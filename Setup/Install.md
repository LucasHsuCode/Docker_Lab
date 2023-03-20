
# Installing Docker on Ubuntu 20.04
Here are the steps to install Docker on Ubuntu 20.04:

1. Update APT package index:
```
sudo apt update
```
2. Install necessary dependencies:
```
sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release
```
3. Add Docker's GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
4. Add Docker's APT repository:
```
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
5. Update APT package index:
```
sudo apt update
```
6. Install Docker:
```
sudo apt install docker-ce docker-ce-cli containerd.io
```
7. Start Docker service:
```
sudo systemctl start docker
```
8. Verify that Docker is running correctly:
```
sudo docker run hello-world
```
If Docker is running correctly, you should see a message that says "Hello from Docker!". This indicates that Docker has been installed successfully.

Note that when using Docker, you need to run relevant commands as root or a user with sudo privileges.

***
在 Ubuntu 20.04 上安裝 Docker 可以遵循以下步驟：
1. 更新 APT 包索引：
```
sudo apt update
```
2. 安裝必要的依賴項：
```
sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release
```
3. 添加 Docker 的 GPG 密鑰：
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
4. 添加 Docker 的 APT 庫：
```
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
5. 更新 APT 包索引：
```
sudo apt update
```
6. 安裝 Docker：
```
sudo apt install docker-ce docker-ce-cli containerd.io
```
7. 啟動 Docker 服務：
```
sudo systemctl start docker
```
8. 確認 Docker 是否正常運行：
```
sudo docker run hello-world
```
如果 Docker 正常運行，你應該能夠看到一個“Hello from Docker!”的消息，這表示 Docker 已經安裝成功了。

需要注意的是，在使用 Docker 時，需要以 root 或者擁有 sudo 權限的用戶身份運行相關命令。
***

