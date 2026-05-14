# iwiki

个人技术成长记录与知识沉淀。

> 这不是一份面试题集，而是一份"我理解了什么"的成长档案。

---

## 📍 学习路径

整个知识库按以下学习阶段推进，各阶段并非严格串行——前一阶段达到"够用"即可进入下一阶段，遇到瓶颈再回头深入。

```
阶段 1：计算机基础
  ├─ network/        计算机网络
  ├─ os/             操作系统
  └─ database/       数据库（关系型）

阶段 2：Go 语言
  └─ go/             基础语法 → 并发 → 进阶 → 服务开发 → 主流框架

阶段 3：存储与中间件
  ├─ database/       SQL 进阶、索引、事务、ES/CK/SR/TiDB
  ├─ cache/          Redis 数据结构、持久化、高可用
  └─ mq/             Kafka / RocketMQ / Pulsar、消息可靠性

阶段 4：分布式与微服务
  └─ distributed/    服务治理、限流熔断、一致性、稳定性

阶段 5：云原生与可观测性
  └─ cloud-native/   Docker、K8s、Prometheus、Trace

阶段 6：系统设计（贯穿全程）
  └─ system-design/  综合训练，把前面学过的串起来

贯穿所有阶段的"职业素养"：
  ├─ engineering/    设计模式 / RESTful / Git / 测试 / Code Review
  ├─ troubleshooting/ pprof / CPU / 内存 / 慢SQL / 事故复盘
  └─ security/       鉴权 / JWT / OAuth / 越权 / Web 攻防

实践配套：
  ├─ project/        完整项目的设计、实现、复盘
  ├─ lab/            动手实验、demo、benchmark
  └─ inbox/          临时收集箱
```

---

## 🎯 各领域入口

| 领域 | 描述 | 入口 |
|---|---|---|
| Go 语言 | 语法、并发、运行时、服务开发、框架生态 | [go/](./go/README.md) |
| 计算机网络 | TCP/IP、HTTP、TLS | [network/](./network/README.md) |
| 操作系统 | 进程、内存、I/O、Linux | [os/](./os/README.md) |
| 数据库 | MySQL / ES / ClickHouse / StarRocks / TiDB | [database/](./database/README.md) |
| 缓存 | Redis、缓存模式、一致性 | [cache/](./cache/README.md) |
| 消息队列 | Kafka / RocketMQ / Pulsar、可靠性 | [mq/](./mq/README.md) |
| 微服务与分布式 | 服务治理、一致性、稳定性 | [distributed/](./distributed/README.md) |
| 云原生 | Docker、K8s、可观测性 | [cloud-native/](./cloud-native/README.md) |
| 系统设计 | 综合设计训练 | [system-design/](./system-design/README.md) |
| 工程实践 | 设计模式 / RESTful / Git / 测试 / Code Review | [engineering/](./engineering/README.md) |
| 故障排查 | pprof / CPU / 内存 / 慢SQL / 事故复盘 | [troubleshooting/](./troubleshooting/README.md) |
| 安全 | 鉴权 / JWT / OAuth / 越权 / Web 攻防 | [security/](./security/README.md) |
| 项目实践 | 完整项目记录 | [project/](./project/README.md) |
| 动手实验 | demo、benchmark | [lab/](./lab/README.md) |
| 临时收集 | 文章、AI 文档、灵感 | [inbox/](./inbox/README.md) |

---

## 📊 全局学习进度

> 各领域问题清单的"自然数量"——按真实复杂度而非整齐凑数。

| 领域 | 问题总数 | 已完成 | 进度 |
|---|---:|---:|---|
| go | 43 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| network | 30 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| os | 33 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| database | 49 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| cache | 26 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| mq | 28 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| distributed | 33 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| cloud-native | 28 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| system-design | 35 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| engineering | 43 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| troubleshooting | 32 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| security | 37 | 0 | ⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜ 0% |
| **合计** | **417** | **0** | **0%** |

> 进度说明：每个领域的进度需要在对应的 README 里手动更新（勾选问题清单），然后回到本表同步。

---

## 📝 笔记规范

### 核心原则

1. **一篇笔记只回答一个问题** —— 标题限定边界
2. **先写"简短回答"再展开** —— 逼自己先想清楚结论
3. **如果正在写的内容换一个问题标题更合适，就停下来新开一篇**
4. **"我的理解"比"标准答案"更重要** —— 这是个人知识库，不是教科书

### 什么层次的知识值得记录？

参见 [什么层次的知识值得记录.md](../什么层次的知识值得记录.md)

### 单篇笔记模板

参见 [TEMPLATE.md](./TEMPLATE.md)

---

## 📐 目录粒度三原则（未来扩展的硬约束）

为了避免未来"为了某个工具就新建一个一级目录"这种越拆越碎的失控，定下三条硬约束：

### 原则 1：按"问题域"拆目录，不按"工具名"拆目录
- ✅ `database/` 装 MySQL / ES / ClickHouse / TiDB
- ❌ 不为 `elasticsearch/` `clickhouse/` 各建独立目录
- 原因：工具会变化，问题域不变

### 原则 2：一级目录总数控制在 ~16 个以内
- 超过 16 个意味着你已经开始在拆"不该独立"的东西
- 新领域优先并入现有目录的子分组，只有问题数达到 ~20+ 才考虑独立

### 原则 3：犹豫建不建新目录时，默认不建
- 先放 `inbox/`，累积几篇后再决定是否析出
- "先放进去再说"比"先建目录再说"不错的多

---

## 🏷️ 命名规范

### 目录命名

| 规则 | 说明 |
|---|---|
| 全部小写英文 | 不用驼峰，不用大写开头 |
| 统一单数 | 表达领域/分类，不表达数量 |
| 多词用连字符 | `cloud-native`、`system-design` |
| 只用公认缩写 | `os`、`mq`、`k8s`、`rpc`、`cicd` 可以；其他写全称 |

### 文件命名

| 规则 | 说明 |
|---|---|
| 中文问题句 | 标题即问题，一眼知道内容 |
| 不加标点符号 | 问号省略，避免跨平台兼容问题 |
| 不加序号 | 避免排序纠结 |
| 扩展名 `.md` | 统一 Markdown |

### 示例

```
go/goroutine是怎么被调度到OS线程上的.md
database/为什么B+树适合做数据库索引.md
cache/Redis的zset底层为什么用跳表而不是红黑树.md
```

### 不允许出现的特殊字符

`?` `*` `:` `<` `>` `|` `"` `/` `\`

---

## 🔄 工作流

```
学习/思考  ──►  inbox/ 临时存放（如果需要）
                  │
                  ▼
            选定一个问题
                  │
                  ▼
        基于 TEMPLATE.md 新建一篇
                  │
                  ▼
        填写"简短回答 → 展开 → 我的理解"
                  │
                  ▼
        在对应领域 README 的问题清单里勾选 ✅
                  │
                  ▼
        回到根 README 同步全局进度（可选，定期批量做）
```

---

## 📌 修订记录

- 2026-05-14：初版，搭建 11 个一级目录，确立命名规范与笔记模板
- 2026-05-14：升级 README 结构——所有领域 README 加入"学习路径 + 核心问题清单 + 进度追踪 + 修订记录"四段式，根 README 新增全局学习进度总览（共 290 个核心问题）
- 2026-05-14：新增 3 个一级目录（engineering / troubleshooting / security）并扩充 go / database / mq 三个领域的子分组；问题总数从 290 提升到 417；加入《目录粒度三原则》作为未来扩展的硬约束
