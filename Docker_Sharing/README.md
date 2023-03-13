
# Docker Sharing Sample

假設我們有一個名為 my-base-image 的基礎鏡像，裡面包含了一個檔案 /app/hello.txt，內容是 "Hello, world!"，Dockerfile 如下：
```
FROM alpine
RUN echo "Hello, world!" > /app/hello.txt
```

我們可以使用 docker build 命令來建立這個鏡像：
```
$ docker build -t my-base-image .

```

現在我們創建一個新的鏡像 my-app-image，基於 my-base-image，並向其中添加一個新的檔案 /app/greeting.txt，內容是 "Welcome to my app!"，Dockerfile 如下：
```
FROM my-base-image
RUN echo "Welcome to my app!" > /app/greeting.txt
```
使用 docker build 命令建立這個鏡像：
```
$ docker build -t my-app-image .
```
當我們查看 my-app-image 的鏡像大小時，會發現它比 my-base-image 大得多：

```
$ docker images
REPOSITORY       TAG       IMAGE ID       CREATED          SIZE
my-app-image     latest    b7ce442d1f37   2 seconds ago    5.59MB
my-base-image    latest    6dbb9cc54074   5 seconds ago    5.58MB

```
但實際上，這兩個鏡像共享一些相同的層，這可以使用 docker history 命令來查看：
```
$ sudo docker history my-app-image

IMAGE          CREATED          CREATED BY                                      SIZE      COMMENT
f9911196055a   6 minutes ago    RUN /bin/sh -c echo "Welcome to my app!" > /…   19B       buildkit.dockerfile.v0
<missing>      41 minutes ago   RUN /bin/sh -c echo "Hello, world!" > /app/h…   14B       buildkit.dockerfile.v0
<missing>      41 minutes ago   RUN /bin/sh -c mkdir /app # buildkit            0B        buildkit.dockerfile.v0
<missing>      4 weeks ago      /bin/sh -c #(nop)  CMD ["/bin/sh"]              0B        
<missing>      4 weeks ago      /bin/sh -c #(nop) ADD file:40887ab7c06977737…   7.05MB    

$ sudo docker history my-base-image

IMAGE          CREATED          CREATED BY                                      SIZE      COMMENT
82010213b42b   41 minutes ago   RUN /bin/sh -c echo "Hello, world!" > /app/h…   14B       buildkit.dockerfile.v0
<missing>      41 minutes ago   RUN /bin/sh -c mkdir /app # buildkit            0B        buildkit.dockerfile.v0
<missing>      4 weeks ago      /bin/sh -c #(nop)  CMD ["/bin/sh"]              0B        
<missing>      4 weeks ago      /bin/sh -c #(nop) ADD file:40887ab7c06977737…   7.05MB    
```
如上所示，my-app-image 鏡像只添加了一個新層，而這個新層之上是 my-base-image 鏡像中的一個層。
因此，Docker 的鏡像共享機制允許不同的鏡像共享它們的相同層，以節省空間和加速鏡像的建立過程。