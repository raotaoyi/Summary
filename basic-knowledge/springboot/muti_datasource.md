```````
数据源切换时最好在try-catch的finally中进行clear或者还原为默认的数据源，防止漏切或者异常导致的切换不及时
````````
```````
数据源切换使用ThreadLocal为每一个线程提供了一个本地的副本变量机制，实现了和其他线程的隔离
```````
