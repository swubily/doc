\1. docker container to image

docker commit <container name> <new image name>

\2. docker file 语法

| WORKDIR          | 工作路径，不要使用RUN CD, 尽量使用绝对路径                   |
| ---------------- | ------------------------------------------------------------ |
| ADD & COPY       | 拷贝本地文件到容器，最好用ADD， ADD有解压功能                |
| CMD & ENTRYPOINT | ENTRYPOINT 肯定会被执行的， CMD是默认会执行一次，用户可以命令行制定CMD 代替 比如 docker run 《container》 /bin/bash   CMD [] 放到 ENTRYPOINT 后面， 可以用来传 run docker 参数 |



\3. docker 常用命令：

| docker exec                                                  | 进入到运行中的docker容器里面，如： docker exec -it <container> /bin/bash |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| docker rm $(docker ps -aq)                                   | 删除所有docker container                                     |
| docker inspect 《container》                                 | 查看contaner详细信息，如果网络信息 ip等                      |
| docker --memory=200M --cpu-shares 10                         | 限制container的内存 cpu等                                    |
| docker --link <name>                                         | docker之间的dns配置，容器内可以直接访问dns名                 |
| doecker -p 80:80                                             | 端口映射，把容器的端口映射到本地的端口                       |
| docker -e MYSQL_HOST=mysql-container                         | 设置容器的环境变量                                           |
| ls /var/run/docker/netns                                     | 查看docker network namespace                                 |
| nsenter  --net=/var/run/docker/netns/ingress_sbox   iptables -nL -t mangle   ipvsadm -l | 进入某个network namespace                                    |
| docker stack deploy 《name》 --compose-file=xxx.yaml         | 在swarm cluster环境下部署 docker-compose编写的容器           |
| docker secret                                                | 设置密码加密                                                 |
| docker service update --image 《image》 《service name》     | 跟新service                                                  |



\4. vagrant 可以基于vitrualbox（或者vmware）创建虚拟机，可以在vagrantfile里面配置shell 在启动虚拟机的时候执行

![graphic](file:///C:/Users/zhanwang/AppData/Local/Temp/enhtmlclip/Image.png)



\5. docker-machine 可以基于vitrualbox （或者阿里云）创建虚拟机，本地的docker client 可以直接访问远程的docker engne



\6. docker swarm实例操作：



\1. 在swarm下， container不在同一个机器下。 这就需要解决网络通信问题。可以通过overlay解决

》》》 docker network create -d overlay demo-network

\2. 创建容器，swarm下不能用docker run，而是应该用docker service create

》》》 docker create --name mysql --env xxx --network --mount type=volume，src=mysql——data， desc=/var/lab/mysql demo-network mysql



Routing Mesh:（Internal 和 Ingress）

Internal

： Load Balancing : docker容器虽然在不同的node上但是可以通过servicename 相互访问，因为service可以很想扩展，所以docker采用了VIP 的方式提供DNS访问



\7. docker 监控：



图形化监控工具（weavescope） 启动方式：scope luanch 《host ips》



二：kubernetes



\1. 常用命令：



| kubectl get pods  [-o wide]                                  | 查看pods                  |
| ------------------------------------------------------------ | ------------------------- |
| kubectl create -f xxx.yaml                                   | 创建pod                   |
| kubectl describe pods <pod name>                             | 查看pod 详情              |
| kubectl port-forward  <pod name>  8080:80                    | 端口转发配置              |
| kubectl scale rc nginx --replicas=2                          | pod scale in、out         |
| kubectl create deployment -f xxx.yaml                        | 部署                      |
| kubectl set image deployment 《deployment name》 《image》=《new image》 | 更新部署的image           |
| kubectl rollout history deployment 《deployment name》       | 查看部署历史              |
| kubectl rollout undo deployment 《deployment name》          | 回滚部署                  |
| kubectl expose deployment 《deployment name》 --type=NodePort | 把pod的端口暴露到外面主机 |
| kubectl get svc                                              | 查看暴露端口信息          |
| kubectl expose deployment 《deployment name》                | 创建 cluster IP  service  |
| kubectl edit deployment 《deployment name》                  | down机更新                |
| rollout                                                      | 不down机更新              |



\2. k8s 下监控（heapster+influxdb+grafana）