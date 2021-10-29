# TheArtOfJavaConcurrencyPrograming
The Art of Java Concurrency Programing



### 1.并发编程的挑战

#### 1.1 上下文切换

单核处理器是通过时间片切换来实现多线程的。线程切换时(线程状态的切换)，需要保存上一个线程的状态，需要开销。

##### 1.1.1 如何减少上下文切换

* 无锁并发编程
* CAS算法
* 使用最少线程,避免创建不需要的线程。
* 协程



#### 1.2 死锁

##### 1.2.1 避免死锁的方法

* 避免一个线程同时获取多个锁
* 避免一个线程在锁内同时占用多个资源，尽量保证每个锁只占用一个资源
* 尝试使用定时锁，使用 lock.tryLock（timeout）来替代使用内部锁机制
* 对于数据库锁，加锁和解锁必须在一个数据库连接里，否则会出现解锁失败的情
  况