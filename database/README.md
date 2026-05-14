# 数据库

> 以 MySQL 为主线，理解关系型数据库的存储、索引、事务、并发控制与高可用机制。

对应学习阶段：
- **阶段 1**：SQL 基础（6-8 周）
- **阶段 4**：数据库深入（8-10 周）

---

## 📍 学习路径

```
阶段一：SQL 与建模（必须掌握）
  ├─ SQL 语法与多表查询
  ├─ 数据类型选择
  ├─ 范式与反范式
  └─ 表结构设计与约束

阶段二：索引与查询优化（核心）
  ├─ B+ 树索引原理
  ├─ 聚簇索引 vs 二级索引
  ├─ 联合索引与最左前缀
  ├─ 覆盖索引与索引下推
  └─ 执行计划与慢查询分析

阶段三：事务与并发控制（深入）
  ├─ ACID 与隔离级别
  ├─ 锁机制（行锁、间隙锁、Next-Key Lock）
  ├─ MVCC 实现原理
  ├─ undo log / redo log / binlog
  └─ 死锁检测与处理

阶段四：高可用与扩展（进阶）
  ├─ 主从复制与读写分离
  ├─ 分库分表
  ├─ 分布式事务
  └─ 数据迁移与一致性

阶段五：超越 MySQL（按场景选型）
  ├─ ES：搜索与全文检索
  ├─ ClickHouse：OLAP 与海量分析
  ├─ StarRocks：实时分析与 HTAP
  └─ TiDB：分布式关系型数据库
```

---

## 🎯 核心问题清单

> 标注：`[ ]` 待开始 / `[/]` 进行中 / `[x]` 已完成

### 阶段一：SQL 与建模
- [ ] 数据库范式到底解决了什么问题
- [ ] 什么时候应该反范式设计
- [ ] varchar 和 char 的区别以及怎么选
- [ ] decimal 和 float 在金额场景下为什么必须用 decimal
- [ ] NULL 在 SQL 中有哪些坑
- [ ] LEFT JOIN 和 INNER JOIN 的执行差异

### 阶段二：索引与查询优化
- [ ] 为什么 MySQL InnoDB 选择 B+ 树而不是 B 树或红黑树
- [ ] 聚簇索引和二级索引的存储结构有什么不同
- [ ] 联合索引的最左前缀原则是怎么生效的
- [ ] 什么是覆盖索引和索引下推
- [ ] 索引为什么会失效有哪些常见情况
- [ ] EXPLAIN 中 type 字段的含义和优先级
- [ ] 慢查询分析的完整流程是什么
- [ ] 为什么不建议用 SELECT \*
- [ ] 单表数据量到多少需要考虑分表
- [ ] 字符串字段加索引前缀长度怎么选

### 阶段三：事务与并发控制
- [ ] ACID 四个特性分别由什么机制保证
- [ ] 四种隔离级别分别解决了什么问题
- [ ] MVCC 是怎么实现读不加锁的
- [ ] ReadView 是什么时候生成的
- [ ] redo log 和 binlog 的两阶段提交是怎么回事
- [ ] undo log 在事务回滚和 MVCC 中分别起什么作用
- [ ] 行锁是加在记录上还是加在索引上
- [ ] 间隙锁是怎么解决幻读的
- [ ] 什么是当前读和快照读
- [ ] 死锁是怎么产生的 MySQL 怎么检测和处理
- [ ] RR 隔离级别下幻读真的被完全解决了吗

### 阶段四：高可用与扩展
- [ ] MySQL 主从复制的原理和延迟来源
- [ ] 半同步复制和异步复制的区别
- [ ] 读写分离会带来哪些问题怎么解决
- [ ] 分库分表的拆分维度怎么选
- [ ] 分库分表后跨库 JOIN 和分页怎么处理
- [ ] 全局唯一 ID 有哪些方案各有什么优劣
- [ ] 分布式事务有哪些常见方案

### 阶段五：超越 MySQL（按场景选型）

#### Elasticsearch（搜索与全文检索）
- [ ] ES 的倒排索引是怎么工作的为什么适合搜索
- [ ] ES 的分片和副本机制以及怎么扩容
- [ ] ES 的近实时搜索 NRT 是怎么实现的
- [ ] ES 和 MySQL 的数据一致性怎么保证
- [ ] 什么场景应该用 ES 什么场景不应该

#### ClickHouse（OLAP 与海量分析）
- [ ] ClickHouse 为什么这么快列存到底快在哪
- [ ] ClickHouse 的 MergeTree 引擎家族各自的适用场景
- [ ] ClickHouse 不适合什么场景为什么不能当 OLTP 用
- [ ] ClickHouse 的物化视图和投影应该怎么用

#### StarRocks（实时分析与 HTAP）
- [ ] StarRocks 的存算分离架构相比 ClickHouse 有什么优势
- [ ] StarRocks 的 MPP 执行引擎是怎么工作的
- [ ] StarRocks 和 Doris 的关系以及该怎么选

#### TiDB（分布式关系型数据库）
- [ ] TiDB 的存算分离架构和 TiKV 的 Raft 实现
- [ ] TiDB 相比传统分库分表的优势和代价
- [ ] TiDB 在什么场景下应该考虑替代 MySQL

### 工程实践
- [ ] online DDL 是怎么做的为什么有的 DDL 仍然会锁表
- [ ] 大表加索引或加字段怎么不影响线上
- [ ] 如何评估一个 SQL 上线前的性能风险
- [ ] 备份与恢复有哪些手段

---

## 📊 学习进度

- 总问题数：49
- 已完成：0 ✅
- 进行中：0 🔄
- 待开始：49 ⏳

---

## 📚 推荐资源

### MySQL
- [MySQL 官方文档](https://docs.oracle.com/cd/E17952_01/index.html)
- [小林 coding - 图解 MySQL](https://xiaolincoding.com/mysql/)
- [《高性能 MySQL》](https://book.douban.com/subject/23008813/)
- [《MySQL 是怎样运行的》](https://book.douban.com/subject/35231266/)
- [极客时间 - MySQL 实战 45 讲](https://time.geekbang.org/column/intro/100020801)

### 其他数据库
- [Elasticsearch 官方文档](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- [ClickHouse 官方文档](https://clickhouse.com/docs)
- [StarRocks 官方文档](https://docs.starrocks.io/zh/docs/introduction/StarRocks_intro/)
- [TiDB 官方文档](https://docs.pingcap.com/zh/tidb/stable/)

---

## 📝 修订记录

- 2026-05-14：初版，列出 35 个核心问题，划分为 4 个学习阶段 + 工程实践
- 2026-05-14：扩充阶段五（超越 MySQL），加入 ES / ClickHouse / StarRocks / TiDB 共 14 个问题，总数 49
