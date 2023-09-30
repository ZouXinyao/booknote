## 基础

### 1、Redis基础数据结构

[Redis 数据结构](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/data_struct/data_struct.html)

[Redis 核心篇：唯快不破的秘密](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6924570137773211662)



### 2、Redis进阶数据结构

Bitmap

[Redis 实战篇：巧用Bitmap 实现亿级海量数据统计](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6999908907791417351)



GEO

[Redis 实战篇：GEO助我邂逅附近女神](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6982466335670272036)



Stream

[别再用 Redis List 实现消息队列了，Stream 专为队列而生](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7070757711926788103)



Bloom Filter

[硬核 | Redis 布隆（Bloom Filter）过滤器原理与实战](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7085229115921399821)



HyperLogLog

[Redis HyperLogLog 是什么？这些场景使用它，让我枪出如龙，一笑破苍穹](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7085952043071832095)



### 3、Redis持久化：日志

AOF、RDB

[Redis 日志篇：宕机快速恢复和持久化实现原理（AOF、RDB）](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6961735998547951653)

[AOF 持久化是怎么实现的？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/storage/aof.html)

[RDB 快照是怎么实现的？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/storage/rdb.html)



### 4、Redis数据过期时如何处理

[Redis 过期删除策略和内存淘汰策略有什么区别？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/module/strategy.html)

[Redis 的数据过期了就会马上删除么？](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7098256190739578911)



### 5、Redis内存问题

[Redis 内存满了怎么办？这样处理才正确](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7124530633782591496)

[Redis 为何使用近似 LRU 算法淘汰数据，而不是真实 LRU？](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7096052937767518222)



### 6、Redis的网络模型（Redis为什么这么快）

[Redis 核心篇：唯快不破的秘密](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6924570137773211662)



### 7、Redis常用的应用

[Redis 常见数据类型和应用场景](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/data_struct/command.html)



## 高可用

### 1、发布/订阅机制

[Redis pub/sub 发布订阅机制原理与实战](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7134591236195188744)



### 2、主从机制

[主从复制是怎么实现的？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/cluster/master_slave_replication.html)

[Redis 高可用篇：主从架构数据一致性同步原理](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6973928120332058654)



### 3、哨兵机制

[为什么要有哨兵？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/cluster/sentinel.html)

[Redis 高可用篇：你管这叫 Sentinel 哨兵集群原理](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7017314970987659300)



### 4、Cluster

[为什么要有集群？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/cluster/cluster.html)

[Redis高可用篇：Cluster集群能支持的数据量有多大？ - 掘金](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7010582783898681357)



## 实践

### 1、缓存失效的处理方法

击穿、穿透、雪崩

[什么是缓存雪崩、击穿、穿透？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/cluster/cache_problem.html)

[图文并茂助力进阶，这次彻底搞懂 Redis 击穿、穿透、雪崩三大难题](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7083748389732499463)



### 2、Redis队列：List、Stream

[把Redis当作队列来用，真的合适吗？](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/RthQvzLHZRGNo-z6X_7jQQ)

[Redis 竟然能用 List 实现消息队列](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7065579246709637150)

[别再用 Redis List 实现消息队列了，Stream 专为队列而生](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7070757711926788103)



### 3、Redis数据统计上的应用

[Redis 实战篇：巧用数据类型实现亿级数据统计](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6993885887704596517)

[Redis 实战篇：巧用Bitmap 实现亿级海量数据统计](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6999908907791417351)



### 4、Redis与MySQL数据一致性问题

[缓存和数据库一致性问题，看这篇就够了](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/4W7vmICGx6a_WX701zxgPQ)

[数据库和缓存如何保证一致性？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/architecture/mysql_redis_consistency.html)

[掘地三尺搞定 Redis 与 MySQL 数据一致性问题](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7110120022848045092)



### 5、Redis分布式锁

[深度剖析：Redis分布式锁到底安全吗？看完这篇文章彻底懂了！](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/s8xjm1ZCKIoTGT3DCVA4aw)

https://zhuanlan.zhihu.com/p/626924850

https://zhuanlan.zhihu.com/p/629247043

### 6、Redis大key的处理

[Redis 大 Key 对持久化有什么影响？](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/storage/bigkey_aof_rdb.html)



### 7、Redis突然变慢怎么排查

[Redis 忽然变慢了如何排查并解决？](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7067732935230619656)

[Redis为什么变慢了？一文讲透如何排查Redis性能问题 | 万字长文](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/Qc4t_-_pL4w8VlSoJhRDcg)

## 进阶

### 1、Redis6.0的多线程机制

[Redis 6.0 新特性：带你 100% 掌握多线程模型](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6989109527886954527)

[Redis 6.0 绝绝子新特性：客户端缓存让性能更上一层楼](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7120054258111610910)



### 2、Redis实现限流



### 3、Redis实现排行榜



### 4、Redis事务

[Redis 事务支持 ACID 么？](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7053013135841558542)



### 5、Redis中的内存优化

[Redis 内存优化神技：小内存保存大数据](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7117930620969287716)



### 6、Redis相关的系统设计：如何抗住大流量读操作。（二级缓存——本地缓存+Redis）





## 综合问题

[读懂Redis源码，我总结了这7点心得](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/Lz7J45jmo3aYAUvg8vStNA)

[颠覆认知——Redis会遇到的15个「坑」，你踩过几个？](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/CHtZI9k2qQ_YJb5Mwzrukw)

[Redis最佳实践：7个维度+43条使用规范，带你彻底玩转Redis | 附实践清单](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/oDV-2IkX16EffLcStT0bSg)

[如何从0到1构建一个稳定、高性能的Redis集群？（附16张图解）](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/q79ji-cgfUMo7H0p254QRg)

[Redis为什么变慢了？一文讲透如何排查Redis性能问题 | 万字长文](http://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/Qc4t_-_pL4w8VlSoJhRDcg)

[Redis 面霸篇：高频问题横扫核心知识点](http://link.zhihu.com/?target=https%3A//juejin.cn/post/6976257378094481444)

[Redis 常见面试题](http://link.zhihu.com/?target=https%3A//www.xiaolincoding.com/redis/base/redis_interview.html)

[Redis 很屌，不懂使用规范就糟蹋了](http://link.zhihu.com/?target=https%3A//juejin.cn/post/7037025652515536927)