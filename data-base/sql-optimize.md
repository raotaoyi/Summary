# sql优化方法（个人经历）
* 根据相应的sql的查询条件创建相应的联合索引或索引
* 可以根据Explain命令(navicat的解释按钮)，查看表的使用情况是否为全查询，尽可能减少连接表的连接数
* 外部的过滤条件，可以往子查询中放，减少各个子表的数据，从而减少各表的连接数
* sql中的条件运用到函数，会使索引失去效果，可以将该函数放在业务层来进行处理(date_format时间处理，subString_index()字符串处理)
* 把固定的sql可以创建临时表
* [ 临时表的造成性能的降低](https://www.cnblogs.com/cchust/p/10891520.html)，产生临时表的情况union，group by，distinct
* between...and..查询的区间过大，索引会失去失效，数据量太大索引失效，没有其他办法
* mysql的not in数据太慢可以使用(io次数太频繁)，可以使用left join进行替代。in同理
````````````````````
-- 查看sql的io次数
flush status;
select * from table
show status like '%hand%'
````````````````````
* 使用多表连接时，注意外键的数据类型是否一样，不一样会导致索引失效，性能下降
* 在mysql优化中，永远是小表驱动大表，join查询在有索引的条件下，驱动表有索引不会使用索引，被驱动表建立索引会使用到索引(推荐)
````````````````````
驱动表的含义
mysql表关联的算法是nest loop join，是通过驱动表的结果集作为循环基础的数据，然后一条一条的通过该结果集中的数据作为过滤条件
到下一表中查询数据，然后合并结果。如果还有第三个参与join，则再通过前两个表的join结果集作为循环基础的数据，再一次通过循环
查询条件到第第三个表中查询数据，如此往复
````````````````````

# 网上教程
* 其中包含了读写分离，缓存，表分区，垂直拆分，水平拆分
    * [MySQL 大表优化方案](https://mp.weixin.qq.com/s/BMQC2oJlhLoeBDtveXgHpw)
# 概念总结
* 视图和临时表的区别

1，一个好的数据表的设计，字段的数据结构，外键等等，
2，explain解释sql语句，查看sql的速度慢的原因，看是否没有用到索引，查看原因
(1)表的创建是否创建了相应的索引
(2)表在多种索引的情况下，mysql默认选用的索引是否是最优的索引，可以使用强制force index
(3)在过滤条件中是否用到了函数，or，between范围太大的情况，过滤条件需要处理的，可以在业务代码中进行处理
(4)多表连接时，查看外键的数据结果是否相同，不一样的结构对性能影响比较大，左连接右连接时，看是否小表驱动大表，驱动表的索引失效
被驱动的表索引会有效果
(5)在查询数据不是实时的要求很高的sql，可以创建零时表，或者采用缓存来来加快性能的需求
(6)对机子性能较好，对数据量较大的，可以将表加载到内存中，来进行计算比如spark来进行本地的计算
3，减少数据库的访问压力，读写分离

mysql函数
group_concat 分组后拼接
substring_index 字符串处理
locate查看字符串在另一个字符串中是否存在 
Date_sub/add 日期向前推或者向后推


