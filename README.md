### 计算机基础
> 进程间通信的方式有哪几种？

管道：管道是一种半双工的通信方式，数据只能单向流动，而且只能在具有亲缘关系的进程间使用。进程的亲缘关系通常是指父子进程关系。
信号：如信号量
消息队列：RabbitMq等
共享内存：redis，UNIX System V等

### Web

> Servlet容器的对比，Tomcat、Jetty、Nginx

### 数据库

> 数据库中索引有哪几种方式？Mysql支持哪些？

  B+树索引，Hash索引，位图索引。Mysql不支持位图索引

> Mysql一次读取大量数据的解决方案？

  目前Java JDBC本身并不支持流式的数据读取，如果一次从数据库中读取大量的数据会消耗大量的内存，并造成数据库的卡顿。对于一般性的查询，可以先根据条件将ID取出，之后根据ID查询每条记录的数据，将大量查询进行分解。对于联表的大量数据查询，目前还没有想到特别好的办法。

> Mysql查询优化


### Java

> `transient` 关键字的作用是什么？

> `volatile` 关键字的作用是什么？

volatile是一种轻量级的锁，它有两个作用，1是保证此变量对于所有线程的立即可见性；二是禁止指令重排序的优化，从而保证变量赋值操作的顺序与代码中的执行顺序一致。

> 如何防止通过反射破坏单例模式？

单例模式有两种方法来进行破坏，分别是反射和序列化。对于反射破坏单例模式的情况，可以在构造函数中对创建对象的次数进行控制，保证只创建一个对象。或者直接使用枚举类型创建单例。对于序列化的方式破话单例模式，需要定义readResolve() 方法来处理。

> Maven的依赖管理规则是怎样的，不同jar包如果出现版本冲突怎么办？循环依赖怎么办？parent与项目依赖重复或者版本冲突怎么办？如何解决？

> 类加载机制？

> ConcurrentHashMap的原理和扩容机制？

### Hibernate

> Hibernate 的缓存机制是什么，通过hibernate取出的对象修改值后不保存，hibernate会不会默认将对象刷新到数据库中？


### Spring

>Spring 的事务传播机制。
