# springboot集成kafka消息中间件
```
流程：
使用kafka，先要创建主题(topic)，分区(Partition默认的分区的个数是1个),如果Producer不指定分区的话，
消息会被随机加载到相应的分区中，消费组来消费的话(其中的消费者数必须小于分区数,并且一个消费者能消费多个分区，
但是一个分区只能被一个消费者消费，消费者也可以指定分区来进行消费，不然会水机分配)，如果消费者的程序程序出现宕机
会导致消费者程序启动监听到topic中有变动，就会继续消费
生成者的概念:
消费者的概念：
   OFFSET： 当前已消费的条数             
   LOGSIZE： 总条数   
   LAG：未消费的条数
```
 * kafka常用的[命令](kafka/kafkaCommand.md)
 * springboot集成kafka是报connect fail，[排查原因](https://blog.csdn.net/fanrenxiang/article/details/82870708)
