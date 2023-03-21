# Docker_Lab

***
這個 repo 是我學習和紀錄 Docker 技術的地方。在這裡，我會分享我對 Docker 的學習心得、實踐經驗和技術筆記，希望能夠對其他人學習 Docker 提供一些幫助和參考。

目前，我的學習目標是考取 Docker Certified Associate 認證，這是 Docker 官方推出的認證考試，用於驗證個人對 Docker 技術的理解和應用能力。通過考試可以證明自己在 Docker 領域具有專業知識和能力，並有助於提升個人職業發展。

在這個 repo 中，我會不斷更新我的 Docker 筆記和相關實踐案例，並分享一些考取 Docker Certified Associate 認證的心得和技巧。如果你對 Docker 技術感興趣，或者正在學習 Docker，歡迎關注這個 repo，一起學習和交流。
***

Domain 1: Orchestration（佔考試 25% 的部分）
內容可能包括以下內容：
* 完成 Swarm 模式集群的設置，包括管理節點和工作節點
* 說明運行容器和運行服務之間的差異
* 演示鎖定 Swarm 集群的步驟
* 將運行個別容器的指令擴展為在 Swarm 下運行服務的指令
* 解釋“docker inspect”命令的輸出
* 使用 YAML 組合文件將應用程序部署轉換為堆棧文件，並使用“docker stack deploy”部署
* 操作運行中的服務堆棧
* 增加副本數量
* 添加網絡，發布端口
* 掛載卷
* 說明運行複製服務和全局服務的區別
* 確定解決服務未部署問題所需的步驟
* 應用節點標籤以演示任務的放置
* 概述 Docker 應用程序與舊系統通信的重要性
* 用“docker service create”演示使用模板的用法。

Domain 2：: Image Creation, Management, and Registry（佔考試20%）
內容可能包括以下內容：
● 描述 Dockerfile 選項 [add、copy、volumes、expose、entrypoint 等)
● 顯示 Dockerfile 的主要部分
● 提供透過 Dockerfile 建立有效映像檔的範例
● 使用 CLI 命令（如 list、delete、prune、rmi 等）來管理映像檔
● 檢查映像檔並使用篩選和格式報告特定屬性
● 演示標記映像檔
● 利用註冊表來儲存映像檔
● 顯示 Docker 映像檔的層
● 使用檔案來建立 Docker 映像檔
● 將映像檔修改為單一層
● 描述映像檔層的運作方式
● 部署註冊表（非建立架構）
● 配置註冊表
● 登入註冊表
● 利用註冊表中的搜尋功能
● 為映像檔打標記
● 推送映像檔至註冊表
● 在註冊表中簽署映像檔
● 從註冊表中拉取映像檔
● 描述映像檔刪除的運作方式
● 從註冊表中刪除映像檔