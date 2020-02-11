* kafka简介
* kafka的安装
* kafka的配置
  * kafka的配置分为[broker]()，[producter]()，[consumer]()三个不同的配置
* kafka的名词解释
   * broker :每一个安装kafka的服务器都可以是一个broker，在kafka的集群中每一个broker都有一个唯一的id值来区别
* kafka作为一个高吞吐的消息中间件和传统的消息中间件一个很大的不同点在于它的日志实际上是以日志的方式默认保存在/kafka/logs文件夹中，虽然有默认的7天的消除机制，但是在数据量大的而磁盘容量不足的情况下，经常出现无法写入的情况。
* kafka consumer
   * 1,consumer group下可以有一个或者多个consumer instance.consumer instance可以是一个线程，也可以是一个进程
   * 2,group.id=group是一个字符串，是唯一标识consumer group的
   * 3,consumer group下订阅的topic下的每一个分区只能分配给某个group下的一个consummer(多个分区可以分配同一个用户，但一个分区不能分配给同一个group下的多个用户，可以分配不同消费组的不同用户)
   * 当分区的信息被消费完时，current-offset=log_end_offset，LAG=0
   
* kafka的常用命令(linux)
   * nohup ./bin/kafka-server-start.sh config/server.properties & 后台不中断启动kafka服务
   * ./kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 【num】 --partitions 【num】 
   --topic 【主题】 创建主题
   * ./kafka-console-producer.sh --broker-list localhost:2181 --topic 【主题】 向kafka发送信息
   * ./kafka-topics.sh --list --zookeeper localhost：2181 查看所有的kafka的topic
   * ./kafka-topics.sh --describe --zookeeper localhost：2181 --topic 【主题】查看指定主题的具体信息
   * ./kafka-topics.sh --zookeeper localhost：2181 --alter --topic 【主题】 --partitions 【num】更改主题的分区数
   
   * ./kafka-consumer-groups.sh --zookeeper localhost:2181 --list 查看旧版本的消费者组
   * ./kafka-consumer-groups.sh --new-consumer --bootstrap-server localhost:9092 --list 查看新的消费者组
   * ./kafka-console-consumer.sh --zookeeper localhost：2181 --topic 【主题】 --from-beginning 从头开始查看消费信息(历史的)
   * ./kafka-console-consumer.sh --zookeeper localhost：2181 --topic 【主题】 查看当前的消费信息(实时的)
   * ./kafka-consumer-groups.sh --bootstrap-server localhost：9092 --describe --group 【消费组】 查看该消费者组还有多少信息未被消费，该消费者者组是新版本的
   * ./kafka-console-consumer.sh --bootstrap-server localhost:9092 --new-consumer --consumer-property group.id=【新消费者组】 --consumer-property client.id=【消费者】 --topic 【主题】创建消费者组和消费者，该消费者组也可以在程序中设置
 
* kafka的常用命令(windows)
  * .\bin\windows\kafka-server-start.bat .\config\server.properties 运行kafka服务
  * .\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1     --topic 【主题】创建主题
  * .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic 【主题】 向kafka发送信息
  * .\bin\windows\kafka-topics.bat --list --zookeeper localhost:2181 查看所有的kafka的topic
  * .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic 【主题】 消费消息(实时的)
  * .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic 【主题】 --from-beginning消费消息(历史的)
  *  查看新的消费者组
  
  
   
   
   
