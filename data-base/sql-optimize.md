# sql优化方法（个人经历）
* 根据相应的sql的查询条件创建相应的联合索引或索引
* 可以根据Explain命令(navicat的解释按钮)，查看表的使用情况是否为全查询，尽可能减少连接表的连接数
* 外部的过滤条件，可以往子查询中放，减少各个子表的数据，从而减少各表的连接数
* sql中的条件运用到函数，会使索引失去效果，可以将该函数放在业务层来进行处理
* 把固定的sql可以创建临时表
* [ 临时表的造成性能的降低](https://www.cnblogs.com/cchust/p/10891520.html)，产生临时表的情况union，group by，distinct
* mysql的not in数据太慢可以使用(io次数太频繁)，可以使用left join进行替代。in同理
````````````````````
-- 查看sql的io次数
flush status;
select * from table
show status like '%hand%'

````````````````````




# 网上教程
* 其中包含了读写分离，缓存，表分区，垂直拆分，水平拆分
    * [MySQL 大表优化方案](https://mp.weixin.qq.com/s/BMQC2oJlhLoeBDtveXgHpw)
# 概念总结
* 视图和临时表的区别
* between...and..查询的区间过大，索引会失去失效，数据量太大索引失效，没有其他办法


