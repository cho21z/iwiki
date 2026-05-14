# Go 语言

> Go 是支撑后端服务的核心工具，本目录系统记录从语法到运行时、从应用到底层的核心问题。

对应学习阶段：
- **阶段 2**：Go 语言基础（8-10 周）
- **阶段 3**：Web / RPC / 服务开发（6-8 周）

---

## 📍 学习路径

```
阶段一：语言基础（先建立可写代码的能力）
   │
   ├─ 类型系统、值与指针、零值
   ├─ slice / map / string 的使用与陷阱
   ├─ 接口与多态（隐式实现、空接口、类型断言）
   ├─ error / panic / recover
   └─ defer 的执行时机与捕获规则
   │
   ▼
阶段二：并发模型（Go 的灵魂）
   │
   ├─ goroutine 的本质
   ├─ channel 的语义与模式
   ├─ sync 包（Mutex / RWMutex / WaitGroup / Once）
   ├─ context 的传播与取消
   └─ 数据竞争与 race detector
   │
   ▼
阶段三：运行时原理（理解才能调优）
   │
   ├─ GMP 调度模型
   ├─ GC 三色标记与写屏障
   ├─ 内存分配器（mcache / mcentral / mheap）
   ├─ 逃逸分析
   └─ slice / map / channel 的底层结构
   │
   ▼
阶段四：工程化与服务开发
   │
   ├─ go mod 依赖管理
   ├─ 单元测试 / benchmark / pprof
   ├─ HTTP 服务（net/http、Gin）
   ├─ gRPC / Protobuf
   └─ 中间件、错误码、配置、鉴权
```

---

## 🎯 核心问题清单

> 列表会随学习深入演化，可增可删。已完成的题目用 `[x]` 标记。

### 阶段一：语言基础

- [ ] [值类型和引用类型在 Go 里到底有什么区别](./值类型和引用类型在Go里到底有什么区别.md)
- [ ] [slice 扩容机制是怎样的为什么有时会出现意外共享底层数组](./slice扩容机制是怎样的为什么有时会出现意外共享底层数组.md)
- [ ] [map 为什么不是并发安全的并发场景下应该怎么用](./map为什么不是并发安全的并发场景下应该怎么用.md)
- [ ] [string 和 []byte 转换为什么会发生内存拷贝什么时候不会](./string和byte转换为什么会发生内存拷贝什么时候不会.md)
- [ ] [interface 的底层结构 iface 和 eface 有什么区别](./interface的底层结构iface和eface有什么区别.md)
- [ ] [interface 的 nil 判断为什么会有坑](./interface的nil判断为什么会有坑.md)
- [ ] [error 应该怎么设计errors.Is 和 errors.As 解决了什么问题](./error应该怎么设计errors.Is和errors.As解决了什么问题.md)
- [ ] [defer 的执行顺序和参数求值时机是怎样的](./defer的执行顺序和参数求值时机是怎样的.md)
- [ ] [panic 后 defer 还会执行吗recover 必须放在哪里](./panic后defer还会执行吗recover必须放在哪里.md)

### 阶段二：并发模型

- [ ] [goroutine 是怎么被调度到 OS 线程上的](./goroutine是怎么被调度到OS线程上的.md)
- [ ] [channel 底层结构与发送接收流程](./channel底层结构与发送接收流程.md)
- [ ] [无缓冲 channel 和有缓冲 channel 的使用场景区别](./无缓冲channel和有缓冲channel的使用场景区别.md)
- [ ] [select 的随机选择是怎么实现的](./select的随机选择是怎么实现的.md)
- [ ] [Mutex 和 RWMutex 的实现原理与适用场景](./Mutex和RWMutex的实现原理与适用场景.md)
- [ ] [sync.Once 是怎么保证只执行一次的](./sync.Once是怎么保证只执行一次的.md)
- [ ] [sync.Pool 的作用是什么为什么 GC 时会被清空](./sync.Pool的作用是什么为什么GC时会被清空.md)
- [ ] [context 的取消是怎么传播的](./context的取消是怎么传播的.md)
- [ ] [常见的 goroutine 泄漏场景有哪些怎么排查](./常见的goroutine泄漏场景有哪些怎么排查.md)
- [ ] [data race 是什么race detector 是怎么工作的](./data_race是什么race_detector是怎么工作的.md)

### 阶段三：运行时原理

- [ ] [GMP 模型中 P 的作用是什么为什么需要 P](./GMP模型中P的作用是什么为什么需要P.md)
- [ ] [goroutine 阻塞在系统调用时调度器怎么处理](./goroutine阻塞在系统调用时调度器怎么处理.md)
- [ ] [work stealing 是怎么工作的](./work_stealing是怎么工作的.md)
- [ ] [Go 的 GC 为什么用三色标记法写屏障解决了什么问题](./Go的GC为什么用三色标记法写屏障解决了什么问题.md)
- [ ] [STW 发生在 GC 的哪些阶段为什么不能完全消除](./STW发生在GC的哪些阶段为什么不能完全消除.md)
- [ ] [逃逸分析是什么如何判断变量是否逃逸](./逃逸分析是什么如何判断变量是否逃逸.md)
- [ ] [Go 的内存分配器是怎么分级管理的](./Go的内存分配器是怎么分级管理的.md)
- [ ] [map 的扩容是渐进式的具体怎么实现](./map的扩容是渐进式的具体怎么实现.md)

### 阶段四：工程化与服务开发

- [ ] [go mod 的版本选择规则MVS 是什么](./go_mod的版本选择规则MVS是什么.md)
- [ ] [单元测试的 table driven 写法和 mock 思路](./单元测试的table_driven写法和mock思路.md)
- [ ] [benchmark 的结果应该怎么读怎么避免被编译器优化掉](./benchmark的结果应该怎么读怎么避免被编译器优化掉.md)
- [ ] [pprof 怎么定位 CPU 和内存问题](./pprof怎么定位CPU和内存问题.md)
- [ ] [Gin 的中间件链是怎么实现的](./Gin的中间件链是怎么实现的.md)
- [ ] [gRPC 的四种通信模式分别适合什么场景](./gRPC的四种通信模式分别适合什么场景.md)
- [ ] [Protobuf 相比 JSON 的优势在哪里](./Protobuf相比JSON的优势在哪里.md)
- [ ] [服务里的错误码应该怎么设计才不会失控](./服务里的错误码应该怎么设计才不会失控.md)
- [ ] [JWT 和 Session 的本质区别什么场景该用哪个](./JWT和Session的本质区别什么场景该用哪个.md)

### 阶段五：微服务框架与生态

- [ ] [Gin Echo Hertz 三个 HTTP 框架的设计差异在哪](./Gin_Echo_Hertz三个HTTP框架的设计差异在哪.md)
- [ ] [go-zero 为什么适合中小团队快速交付微服务](./go-zero为什么适合中小团队快速交付微服务.md)
- [ ] [Kratos 的分层设计和依赖注入机制是怎样的](./Kratos的分层设计和依赖注入机制是怎样的.md)
- [ ] [Kitex 和 gRPC-Go 在性能和生态上的取舍](./Kitex和gRPC-Go在性能和生态上的取舍.md)
- [ ] [为什么字节要自研 Hertz 而不直接用 Gin](./为什么字节要自研Hertz而不直接用Gin.md)
- [ ] [Kratos 和 go-zero 和 Kitex 选型的决策依据](./Kratos和go-zero和Kitex选型的决策依据.md)
- [ ] [在业务代码中用原生 net/http 还是框架怎么选](./在业务代码中用原生_net_http还是框架怎么选.md)

---

## 📊 学习进度

- 总问题数：43
- 已完成：0 ✅
- 进行中：0 🔄
- 待开始：43 ⏳

---

## 📚 推荐资源

- [A Tour of Go](https://go.dev/tour/)
- [Effective Go](https://go.dev/doc/effective_go)
- [Go by Example](https://gobyexample.com/)
- [《Go语言设计与实现》](https://draven.co/golang/docs/)
- [Gin 文档](https://gin-gonic.com/zh-cn/docs/)
- [gRPC Go 文档](https://grpc.io/docs/languages/go/)
- [go-zero 文档](https://go-zero.dev/zh-cn/)
- [Kratos 文档](https://go-kratos.dev/zh-cn/docs/)
- [CloudWeGo Kitex](https://www.cloudwego.io/zh/docs/kitex/overview/)
- [CloudWeGo Hertz](https://www.cloudwego.io/zh/docs/hertz/overview/)

---

## 📝 修订记录

- 2026-05-14：初版，列出 36 个核心问题，覆盖语言基础 / 并发模型 / 运行时原理 / 工程化与服务开发四个阶段。
- 2026-05-14：新增阶段五（微服务框架与生态），加入 go-zero / Kratos / Kitex / Hertz 对比卡 7 个，总数 43
