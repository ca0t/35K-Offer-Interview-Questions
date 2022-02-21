## String、String Buffer和String Build的区别，怎么保证线程安全

String、String buffer和String Build都是通过char类型数组实现的，只不过String添加了final修饰，所以String变量定义了后不可变，如果对String变量进行**频繁**的修改、拼接等操作，会产生大量的GC回收，很占用系统的资源。

String Buffer和String Build调用同一父类append方法，采用相同的扩容机制，保证了性能开销。

String Buffer是线程安全的，String Build是非线程安全的。String Buffer在所有操作类的方法上添加了synchronized来保证线程安全。

所以String Buffer要比String Build慢一些，在不考虑线程安全的情况下，尽量使用String Build。

## 什么是锁

jvm中一个对象的对象头包含gc状态、对象布局、类型、同步状态、哈希标识基本信息。

锁就是改变对象的对象头中的同步状态。

参考：（http://openjdk.java.net/groups/hotspot/docs/HotSpotGlossary.html） object header

## 什么是死锁

## synchronized原理是什么

## synchronized怎么用的

## synchronized锁优化，锁粗化，锁消除

## 什么是自旋锁

## 什么是偏向锁

在无锁状态下，一个线程进来争夺锁资源，将线程id写入对象头markword中，无锁升级为偏向锁。

jvm在启动后，默认延迟4秒后启动偏向锁。如果在五状态下给对象添加synchronized关键字，对象会直接升级为轻量级锁。

## 什么是轻量级锁

在多个线程争夺锁资源的情况下，cas轻度竞争，偏向锁升级为轻量级锁。

## 什么是重量级锁

cas竞争失败，多线程自旋，线程id进入等待队列，轻量级锁升级为重量级锁

## synchronized和volatile的区别是什么

## 为什么要用volatile

## 说一说Java内存模型

## 说一说Java并发包

## failfast和failsafe区别

## 什么是copyOnWrite

## 什么是AQS

## 什么是CAS

cas可以称为无锁、自旋锁、乐观锁、轻量级锁、compareAndSet、compareAndSwap。

cas机制为先比较，再设置/交换。

## 什么是乐观锁

## 什么是悲观锁

## 乐观锁和悲观锁是怎么实现的，区别是什么

## 什么是行级锁

## 什么是表级锁

## 什么是共享锁

## 什么是排他锁

## 什么是gap锁

## 什么是next key lock

## 数据库的隔离级别有哪些

## 说一说数据库的索引

## 什么是聚簇索引

## 什么是非聚簇索引

## 什么是最左前缀

## 索引如何实现的

## 什么是哈希索引

## 什么是B+树，如何实现的

## B+树里面的存储是怎么存的

## 为什么要用B+树

## 什么是回表

## 什么是分布式锁

## 分布式锁如何实现的

## 数据库，redis，zookeeper实现分布式锁的区别是什么，各自有什么优缺点

## 为什么要使用redis

## 什么是分布式缓存

## redis和memcache有什么区别

## zookeeper怎么实现分布式锁

## 什么是zookeeper

## 什么是cap

## 为什么cap不能同时存在

## 什么是base理论

## 分布式系统如何保证数据一致性

## 分布式数据一致性有哪些算法

## 什么是paxos算法

## 
