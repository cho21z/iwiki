# 消息队列

> 异步化、解耦、削峰填谷的核心基础设施。本目录以 **Kafka** 为主线，理解 MQ 的通用模型与可靠性保证。

对应学习阶段：**阶段 4** —— 数据库 / 缓存 / MQ（8-10 周）

---

## 📍 学习路径

```
阶段一：MQ 基础模型
  ├─ 为什么需要 MQ（异步、解耦、削峰）
  ├─ 核心概念（Producer / Consumer / Broker / Topic / Partition）
  └─ 推模式 vs 拉模式

阶段二：Kafka 架构与存储
  ├─ Broker / Partition / Replica
  ├─ 日志存储结构（segment / index）
  └─ 顺序写 + 零拷贝为何这么快

阶段三：可靠性与一致性
  ├─ ACK 机制与 ISR
  ├─ 消息丢失的三个环节
  ├─ 重复消费与幂等
  └─ 顺序性保证

阶段四：消费者与高级特性
  ├─ 消费者组与 Rebalance
  ├─ Offset 提交策略
  ├─ 死信队列、延迟消息
  └─ 事务消息

阶段五：主流 MQ 对比与选型
  ├─ Kafka vs RocketMQ vs Pulsar
  ├─ 存储模型差异与设计取舍
  └─ 场景化选型决策
```

---

## 🎯 核心问题清单

### 阶段一：基础模型
- [ ] [为什么需要消息队列它解决了什么问题](./为什么需要消息队列它解决了什么问题.md)
- [ ] [MQ的推模式和拉模式各有什么优劣](./MQ的推模式和拉模式各有什么优劣.md)
- [ ] [Topic和Partition的关系是什么](./Topic和Partition的关系是什么.md)

### 阶段二：Kafka 架构与存储
- [ ] [Kafka的整体架构是怎样的](./Kafka的整体架构是怎样的.md)
- [ ] [Kafka的Partition和Replica是怎么分布的](./Kafka的Partition和Replica是怎么分布的.md)
- [ ] [Kafka的日志存储结构是怎样的](./Kafka的日志存储结构是怎样的.md)
- [ ] [Kafka为什么这么快](./Kafka为什么这么快.md)
- [ ] [Kafka的零拷贝是怎么实现的](./Kafka的零拷贝是怎么实现的.md)

### 阶段三：可靠性与一致性
- [ ] [Kafka的ACK机制有几种语义](./Kafka的ACK机制有几种语义.md)
- [ ] [ISR机制是怎么工作的](./ISR机制是怎么工作的.md)
- [ ] [Kafka在哪些环节可能丢消息怎么避免](./Kafka在哪些环节可能丢消息怎么避免.md)
- [ ] [消息重复消费是怎么产生的怎么解决](./消息重复消费是怎么产生的怎么解决.md)
- [ ] [Kafka怎么保证消息的顺序性](./Kafka怎么保证消息的顺序性.md)
- [ ] [生产端的幂等性是怎么实现的](./生产端的幂等性是怎么实现的.md)

### 阶段四：消费者与高级特性
- [ ] [消费者组与Rebalance机制是怎样的](./消费者组与Rebalance机制是怎样的.md)
- [ ] [Rebalance会带来什么问题怎么优化](./Rebalance会带来什么问题怎么优化.md)
- [ ] [Offset的提交策略有哪几种](./Offset的提交策略有哪几种.md)
- [ ] [消息积压了怎么处理](./消息积压了怎么处理.md)
- [ ] [死信队列的作用和实现方式](./死信队列的作用和实现方式.md)
- [ ] [延迟消息可以怎么实现](./延迟消息可以怎么实现.md)
- [ ] [Kafka的事务消息是怎么实现的](./Kafka的事务消息是怎么实现的.md)

### 阶段五：主流 MQ 对比与选型
- [ ] [Kafka 和 RocketMQ 和 Pulsar 的架构本质差异在哪](./Kafka和RocketMQ和Pulsar的架构本质差异在哪.md)
- [ ] [RocketMQ 为什么设计了 NameServer 而不用 ZooKeeper](./RocketMQ为什么设计了NameServer而不用ZooKeeper.md)
- [ ] [RocketMQ 的事务消息和 Kafka 的事务消息不是同一件事](./RocketMQ的事务消息和Kafka的事务消息不是同一件事.md)
- [ ] [RocketMQ 原生支持延时消息是怎么做到的](./RocketMQ原生支持延时消息是怎么做到的.md)
- [ ] [Pulsar 的存算分离架构相比 Kafka 有什么优势](./Pulsar的存算分离架构相比Kafka有什么优势.md)
- [ ] [业务中什么场景选 Kafka 什么场景选 RocketMQ](./业务中什么场景选Kafka什么场景选RocketMQ.md)
- [ ] [Redis Stream 能代替 MQ 吗什么场景下可以](./RedisStream能代替_MQ吗什么场景下可以.md)

---

## 📊 学习进度

- 总问题数：28
- 已完成：0 ✅
- 进行中：0 🔄
- 待开始：28 ⏳

---

## 📚 推荐资源

- [Kafka Docs](https://kafka.apache.org/documentation/)
- [apache/kafka](https://github.com/apache/kafka)
- [RocketMQ 官方文档](https://rocketmq.apache.org/zh/docs/)
- [Apache Pulsar 官方文档](https://pulsar.apache.org/docs/)
- [《Kafka 权威指南》](https://book.douban.com/subject/27665114/)
- [《深入理解 Kafka：核心设计与实践原理》](https://book.douban.com/subject/30437872/)

---

## 📝 修订记录

- 2026-05-14：初版，列出 21 个核心问题
- 2026-05-14：新增阶段五（主流 MQ 对比与选型），加入 RocketMQ 与 Pulsar 对比卡 7 个，总数 28
