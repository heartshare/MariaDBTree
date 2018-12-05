# MariaDBTree
MariaDB技术研究


<pre>
MariaDB是MySQL源代码的一个分支，主要由开源社区维护。甲骨文收购MySQL后，有将MySQL闭源的风险
，因此社区采用分支的方式来避开这个风险。MariaDB完全兼容MySQL。

在存储引擎层面，使用XtraDB来代替MySQL的InnoDB，XtraDB完全兼容InnoDB.
</pre>

<pre>
MariaDB不仅仅是MySQL的替代品。它的主要目的是创新和提高MySQL技术。
     除了包含标准的MyISAM、BLACKHOLE、CSV、MEMORY、ARCHIVE和MERGE等存储引擎外，引入了一
     些新功能（多源复制，基于表的并行复制，Galera集群，Spider水平分片存储引擎，TokuDB存储引擎）
</pre>

<pre>
在Oracle控制下的MySQL开发，有两个主要问题：
      1）MySQL核心开发团队是闭源的，完全没有Oracle之外的成员参加。
      2）MySQL新版本的发布速度，在Oracle收购之后大为减缓。
</pre>

<pre>
1) 引入了Group commit for the binary log组提交技术，简单的说，多个并发提交的事务加入
一个队列里，对这个队列里的事务，利用一次I/O合并提交，从而解决了写日志频繁刷磁盘的问题。
2）引入了基于表的多线程并行复制技术
3）引入了线程池thread pool技术
5）MariaDB用Aria引擎代替了MyISAM引擎，这将使某些GROUP BY和DISTINCT请求速度更快，因
为Aria有比MyISAM更好的缓存机制
</pre>