# 条件判断
# 常见的sql语句
* date_format(colum,'%Y-%m-%d')时间转换
* ifnull(),判空处理
* round()取小数点的位数
* if('language'='c' or 'language'='C++','C&C++',language)，不能使用if(colum=null,a,b),使用if(colum is null,a,b)
* substring_index(tool,'_',1) 截取tool字段的第一个斜杠之前的字符串
* concat连接字符串
* group...by...having
* unix_timestamp(colum),将字段的时间转化成秒
* now()当前时间
* max()去最大值
* count（colum）统计,改函数在统计时具有去重的效果，要注意
* date_sub（）日期减，date_add（）日期加，datediff(a,b)两者日期相差了多少天，date_sub（currentdate()，interval 1 day ）前一天的日期
* currentDate()当前时间
* mybatis中大于和小于号的处理方式有两种
   * &gt； &lt；
   * <![ CDATA[sql语句]]]
```
        <choose>
            <when test="param.level==''"></when>
            <otherwise></otherwise>
        </choose> 
```
```
     <if test="param.product!=null and param.product!=''"></if>
``` 
```    
        select * from t_mc_job_info where register_key in
        <foreach collection="registerKeys" item="item" index="index" 
        open="(" separator="," close=")">
            #{item}
        </foreach>
 ``` 
 ```
        select * from
        (
        <foreach collection="times" item="item" 
                 separator="union all" >
            select * from t_mc_job_info where date=#{item}
        </foreach>
        )
```
* 在MySQL数据库中，如果在insert语句后面带上ON DUPLICATE KEY UPDATE 子句，而要插入的行与表中现有记录的惟一索引或主键中产生重复值，那么就会发生旧行的更新；如果插入的行数据与现有表中记录的唯一索引或者主键不重复，则执行新纪录插入操作。
```
insert into kid_score(id, birth_day, score) values (1,'2019-01-15',30) ON DUPLICATE KEY UPDATE score = score + 50;
```
