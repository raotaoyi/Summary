
* Docker的三大基本概念
  * Docker image：镜像
  * Docker container：容器
  * Docker hub/register:仓库
```
镜像和容器的概念可以理解为：类和实例化的对象，镜像源是不变的，但是这个镜像可以创建不同命的容器，
每个容器即为一个进程，每个容器的程序环境需要自己搭建
```  
* 流程：
```
Docker的pull命令从配置文件中配置的仓库中拉取镜像到本地仓中，
但Docker run的命令是，将镜像放到新建容器中，并且启动这个容器。
存在了该容器，下一次启动时就可以使用Docker start；
```
* 常见的命令
  * 查看所有的容器：docker ps
  * 创建新的容器并且运行容器在后台： docker run -itd --name=【容器名】【镜像名】 bash
  * 启动已存在的容器：docker start 【容器名】
  * 进入容器： docker exec -it 【容器的id】 bash
  
  

  

