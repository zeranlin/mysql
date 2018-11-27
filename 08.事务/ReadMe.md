# MYSQL事务 - 隔离级别

## 事务是什么：    
    1. 一组SQL执行，要么全部成功，要么全部失败    
    2. 事务在存储引擎层面实现的
    3. 事务ACID特性    
        * 原子性 （ Atomicity ) ：一个事务不可分割
        * 一致性 （ Consistency )　： 从一种状态转到另一种状态
        * 隔离性 （ Isolation ） ： 事务提交之前，其他事务不可见
        * 持有性 （ Durability ) ： 一旦事务提交，更新保存数据库


## 隔离级别
    1. 读未提交 ( Read Uncommitted )
    2. 读已提交 ( Read Committed )
    3. 可重复读 ( Repeatable Read )
    4. 可串行化 ( Serializable )

## 隔离级别示意图

![流程示意图](imgs/mysql-08-01.jpg)
    事务B读取了事务A还没有提交的数据

![流程示意图](imgs/mysql-08-02.jpg)
    事务B只能读取到事务A已经提交的事务

![流程示意图](imgs/mysql-08-03.jpg)
    事务B在自己事务开始、结束起脚，读取的数据都是一样的，即使改数据已经被别的事务修改了。

 ![流程示意图](imgs/mysql-08-04.jpg)
     事务B要读取关联数据的前提是，没有任务事务对这个关联数据有进程读取操作。
