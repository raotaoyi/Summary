* kafka简介
* kafka的安装
* kafka的配置
  * kafka的配置分为[broker]()，[producter]()，[consumer]()三个不同的配置
* kafka的名词解释
   * broker :每一个安装kafka的服务器都可以是一个broker，在kafka的集群中每一个broker都有一个唯一的id值来区别
* kafka作为一个高吞吐的消息中间件和传统的消息中间件一个很大的不同点在于它的日志实际上是以日志的方式默认保存在/kafka/logs文件夹中，虽然有默认的7天的消除机制，但是在数据量大的而磁盘容量不足的情况下，经常出现无法写入的情况。
* kafka consumer
   * 1,consumer group下可以有一个或者多个consumer instance.consumer instance可以是一个线程，也可以是一个进程
   
