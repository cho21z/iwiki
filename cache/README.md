# 缓存（Redis）

> 用内存换性能，用一致性换吞吐——理解 Redis 不仅是会用命令，更是理解"为什么这样设计"。

对应学习阶段：**阶段 4** —— 数据库 / 缓存 / MQ（8-10 周）

---

## 📍 学习路径

```
阶段一：会用（基础数据结构与命令）
  ├─ 五大基础类型与典型场景
  ├─ 常用命令与时间复杂度
  └─ 过期与淘汰

阶段二：理解（底层实现与机制）
  ├─ 底层数据结构（SDS、跳表、压缩列表、字典、quicklist）
  ├─ 单线程模型与多路复用
  ├─ 持久化（RDB / AOF）
  └─ 内存管理与淘汰策略

阶段三：用对（缓存模式与三大问题）
  ├─ 缓存读写模式
  ├─ 缓存击穿、穿透、雪崩
  ├─ 缓存与数据库一致性
  └─ 分布式锁

阶段四：用稳（高可用与扩展）
  ├─ 主从复制
  ├─ 哨兵 Sentinel
  ├─ Cluster 集群与分片
  └─ 多级缓存与本地缓存
```

---

## 🎯 核心问题清单

### 阶段一：会用

- [ ] [Redis 的五种基础数据类型分别适合什么场景](./Redis的五种基础数据类型分别适合什么场景.md)
- [ ] [Redis 为什么这么快](./Redis为什么这么快.md)
- [ ] [Redis 的过期键是怎么被删除的](./Redis的过期键是怎么被删除的.md)
- [ ] [Redis 有哪些内存淘汰策略以及它们的区别](./Redis有哪些内存淘汰策略以及它们的区别.md)

### 阶段二：理解

- [ ] [Redis 的字符串为什么不直接用 C 字符串而要自己设计 SDS](./Redis的字符串为什么不直接用C字符串而要自己设计SDS.md)
- [ ] [Redis 的 zset 底层为什么用跳表而不是红黑树](./Redis的zset底层为什么用跳表而不是红黑树.md)
- [ ] [Redis 的 hash 底层是怎么从 ziplist 演变为 hashtable 的](./Redis的hash底层是怎么从ziplist演变为hashtable的.md)
- [ ] [Redis 的字典是怎么进行渐进式 rehash 的](./Redis的字典是怎么进行渐进式rehash的.md)
- [ ] [Redis 单线程为什么还能这么快以及它真的是单线程吗](./Redis单线程为什么还能这么快以及它真的是单线程吗.md)
- [ ] [Redis 的 RDB 和 AOF 各自的工作机制和取舍](./Redis的RDB和AOF各自的工作机制和取舍.md)
- [ ] [Redis 的 AOF 重写为什么不会阻塞主线程](./Redis的AOF重写为什么不会阻塞主线程.md)
- [ ] [Redis 的 bigkey 和 hotkey 会带来什么问题以及怎么排查](./Redis的bigkey和hotkey会带来什么问题以及怎么排查.md)

### 阶段三：用对

- [ ] [Cache Aside、Read Through、Write Through、Write Behind 的区别](./CacheAside和ReadThrough和WriteThrough和WriteBehind的区别.md)
- [ ] [缓存穿透是怎么发生的以及怎么防](./缓存穿透是怎么发生的以及怎么防.md)
- [ ] [缓存击穿和缓存雪崩的区别以及怎么防](./缓存击穿和缓存雪崩的区别以及怎么防.md)
- [ ] [缓存与数据库的一致性问题先删缓存还是先更新数据库](./缓存与数据库的一致性问题先删缓存还是先更新数据库.md)
- [ ] [为什么推荐用延迟双删而不是直接更新缓存](./为什么推荐用延迟双删而不是直接更新缓存.md)
- [ ] [基于 Redis 的分布式锁怎么设计才安全](./基于Redis的分布式锁怎么设计才安全.md)
- [ ] [Redlock 算法是怎么工作的以及它有什么争议](./Redlock算法是怎么工作的以及它有什么争议.md)
- [ ] [Redis 的 Lua 脚本为什么能保证原子性](./Redis的Lua脚本为什么能保证原子性.md)
- [ ] [布隆过滤器是怎么工作的以及在缓存中怎么用](./布隆过滤器是怎么工作的以及在缓存中怎么用.md)

### 阶段四：用稳

- [ ] [Redis 主从复制的全量同步和增量同步流程](./Redis主从复制的全量同步和增量同步流程.md)
- [ ] [Redis 哨兵是怎么实现自动故障转移的](./Redis哨兵是怎么实现自动故障转移的.md)
- [ ] [Redis Cluster 是怎么做数据分片的为什么是 16384 个槽](./RedisCluster是怎么做数据分片的为什么是16384个槽.md)
- [ ] [Redis Cluster 在节点扩缩容时数据是怎么迁移的](./RedisCluster在节点扩缩容时数据是怎么迁移的.md)
- [ ] [多级缓存的设计思路以及本地缓存和 Redis 怎么配合](./多级缓存的设计思路以及本地缓存和Redis怎么配合.md)
- [ ] [Redis Pipeline 和事务以及 MULTI/EXEC 的区别](./RedisPipeline和事务以及MULTI和EXEC的区别.md)

---

## 📊 学习进度

- 总问题数：26
- 已完成：0 ✅
- 进行中：0 🔄
- 待开始：26 ⏳

---

## 📚 推荐资源

- [Redis Docs](https://redis.io/docs/latest/)
- [《Redis设计与实现》黄健宏](https://huangz.works/redisbook1e/)
- [小林 coding - 图解 Redis](https://xiaolincoding.com/redis/)
- [Redis 官方命令参考](https://redis.io/commands/)

---

## 📝 修订记录

- 2026-05-14：初版，列出 26 个核心问题，划分四个阶段
