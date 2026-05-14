# 云原生与可观测性

> 把服务"装进容器、跑在编排平台上、看得见、改得动"——从能用到能稳定运行的关键一公里。

对应学习阶段：**阶段 6** —— 云原生与可观测性（4-6 周）

---

## 📍 学习路径

### 阶段一：容器基础（先理解"容器到底是什么"）
理解容器的本质（namespace + cgroup），再去用 Docker；不要把 Docker 当黑盒。

### 阶段二：Kubernetes 核心对象（从单机到集群）
先掌握 Pod / Deployment / Service / ConfigMap 这四件套，能看懂 yaml、能 kubectl 排查问题。

### 阶段三：可观测性三支柱（Metrics / Traces / Logs）
理解三者的定位差异，能给一个服务搭出最小可用的监控体系。

### 阶段四：CI/CD 与交付（让代码自动化地变成线上服务）
从手动 docker build 到流水线自动发布，理解每一步在做什么。

### 阶段五：性能分析与稳定性（线上问题怎么定位）
pprof、压测、瓶颈分析，把"出了问题"变成"能定位、能解决"。

---

## 🎯 核心问题清单

> 共 28 个核心问题，按学习路径分组。打勾表示已完成。

### 阶段一：容器基础

- [ ] [容器和虚拟机的本质区别是什么](./容器和虚拟机的本质区别是什么.md)
- [ ] [Linux的namespace和cgroup分别解决了什么问题](./Linux的namespace和cgroup分别解决了什么问题.md)
- [ ] [Docker镜像的分层机制是怎么工作的](./Docker镜像的分层机制是怎么工作的.md)
- [ ] [Dockerfile中常见指令对镜像层的影响](./Dockerfile中常见指令对镜像层的影响.md)
- [ ] [如何编写一个体积小且安全的Go服务镜像](./如何编写一个体积小且安全的Go服务镜像.md)

### 阶段二：Kubernetes 核心对象

- [ ] [Pod为什么是K8s的最小调度单位而不是容器](./Pod为什么是K8s的最小调度单位而不是容器.md)
- [ ] [Deployment和ReplicaSet和Pod三者的关系](./Deployment和ReplicaSet和Pod三者的关系.md)
- [ ] [Service的ClusterIP和NodePort和LoadBalancer区别](./Service的ClusterIP和NodePort和LoadBalancer区别.md)
- [ ] [K8s中的Service是如何把流量路由到Pod的](./K8s中的Service是如何把流量路由到Pod的.md)
- [ ] [ConfigMap和Secret的使用场景与差异](./ConfigMap和Secret的使用场景与差异.md)
- [ ] [K8s的滚动更新和回滚是如何实现的](./K8s的滚动更新和回滚是如何实现的.md)
- [ ] [readinessProbe和livenessProbe分别在解决什么问题](./readinessProbe和livenessProbe分别在解决什么问题.md)
- [ ] [K8s的资源requests和limits对调度和OOM的影响](./K8s的资源requests和limits对调度和OOM的影响.md)
- [ ] [HPA是如何根据指标自动扩缩容的](./HPA是如何根据指标自动扩缩容的.md)

### 阶段三：可观测性三支柱

- [ ] [Metrics和Logs和Traces三者的定位差异](./Metrics和Logs和Traces三者的定位差异.md)
- [ ] [Prometheus的数据模型和拉模式设计](./Prometheus的数据模型和拉模式设计.md)
- [ ] [PromQL中rate和irate和increase的区别](./PromQL中rate和irate和increase的区别.md)
- [ ] [四大黄金指标和RED方法分别是什么](./四大黄金指标和RED方法分别是什么.md)
- [ ] [分布式链路追踪中TraceID和SpanID是如何传递的](./分布式链路追踪中TraceID和SpanID是如何传递的.md)
- [ ] [OpenTelemetry为什么要统一三支柱](./OpenTelemetry为什么要统一三支柱.md)
- [ ] [结构化日志相比文本日志的优势](./结构化日志相比文本日志的优势.md)
- [ ] [告警规则的设计原则与降噪策略](./告警规则的设计原则与降噪策略.md)

### 阶段四：CI/CD 与交付

- [ ] [CI和CD和CD三者的边界与目标](./CI和CD和CD三者的边界与目标.md)
- [ ] [蓝绿发布和金丝雀发布和滚动发布的取舍](./蓝绿发布和金丝雀发布和滚动发布的取舍.md)
- [ ] [一条典型的容器化服务交付流水线包含哪些环节](./一条典型的容器化服务交付流水线包含哪些环节.md)

### 阶段五：性能分析与稳定性

- [ ] [Go的pprof能采集哪些维度的数据](./Go的pprof能采集哪些维度的数据.md)
- [ ] [线上CPU飙高如何定位](./线上CPU飙高如何定位.md)
- [ ] [线上内存持续增长如何定位泄漏点](./线上内存持续增长如何定位泄漏点.md)
- [ ] [一次完整的压测流程包含哪些步骤](./一次完整的压测流程包含哪些步骤.md)

---

## 📊 学习进度

- 总问题数：28
- ✅ 已完成：0
- 🔄 进行中：0
- ⏳ 待开始：28

---

## 📝 修订记录

- 2026-05-14：初版，列出 28 个核心问题，覆盖容器、K8s、可观测性、CI/CD、性能分析五个阶段

---

## 推荐资源

- [Kubernetes Docs](https://kubernetes.io/zh/docs/home/)
- [Prometheus Docs](https://prometheus.io/docs/introduction/overview/)
- [OpenTelemetry Docs](https://opentelemetry.io/zh/docs/)
- [Jaeger](https://www.jaegertracing.io/)
- [Google SRE Workbook](https://sre.google/workbook/table-of-contents/)
