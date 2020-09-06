
## java相关

---

### 一、基础


* 基本语法

	基本数据类型；运算符；表达式；选择与循环语句；类与对象（普通类、抽象类、接口、枚举、Annotation、内部类）；继承与实现；异常；package与jar包；序列化与反序列化；正则表达式；重载与覆盖；
* 数组

	一维数组；二维数组。。。
* 集合
	
	Collection接口；Set相关；List相关；Map相关
* 线程

	Thread；Runnable；Callable；线程状态；优先级；
* IO

	File类；字节流（InputStream、OutputStream）；字符流（Reader、Writer）；转换流（OutputStreamWriter、InputStreamReader）；压缩流；

* 网络
	
	TCP编程；UDP编程
* 泛型
* 反射
JAVA反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；
对于任意一个对象，都能够调用它的任意一个方法和属性；
这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制。</br>
用途：提供api方法取得类的结构；调用类的方法；动态代理
* 首先,两者本质上的区别是:静态方法是在类中使用static修饰的方法,
在类定义的时候已经被装载和分配。而非静态方法是不加static关键字的方法,
在类定义时没有占用内存,只有在类被实例化成对象时,对象调用该方法才被分配内存。

* 对象锁（实例锁，synchronized）
该锁针对的是该实例对象（当前对象）。
synchronized是对类的当前实例（当前对象）进行加锁，防止其他线程同时访问该类的该实例的所有synchronized块。
每个对象都有一个锁，且是唯一的。

* 类锁（又称全局锁，static synchronized）
该锁针对的是类，无论实例出多少个对象，那么线程依然共享该锁。
static synchronized是限制多线程中该类的所有实例同时访问该类所对应的代码块。
