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
