# Demonstrate steps to lock a swarm cluster
###演示鎖定 Swarm 集群的步驟

Docker Swarm 的 autolock 是一種自動鎖定機制，用於防止 Docker Swarm 集群中的敏感資訊被未授權的人訪問。當您啟用 Swarm 的 autolock 時，如果某個管理節點（manager node）停止工作，Docker Swarm 將自動將集群鎖定，從而保護敏感資訊。

在 Docker Swarm 中，管理節點負責管理 Swarm 集群的狀態和配置。管理節點還存儲敏感資訊，如證書、密碼和金鑰。如果管理節點被攻擊或停止工作，未授權的人可能會訪問這些敏感資訊，從而對您的 Swarm 集群造成損害。

為了保護敏感資訊，Docker Swarm 提供了 autolock 機制。當您啟用 Swarm 的 autolock 時，Docker Swarm 會自動將集群鎖定，從而保護敏感資訊。如果管理節點停止工作，Docker Swarm 將自動鎖定集群，從而防止未授權的人訪問敏感資訊。在這種情況下，只有當您手動解鎖集群後，才能重新啟動 Swarm 集群。

您可以使用以下命令啟用 Swarm 的 autolock：
```
$ docker swarm init --autolock         // 初始化swarm集群時啟用 autolock
$ docker swarm update --autolock=true  // 在現有的swarm集群啟用 autolock
```