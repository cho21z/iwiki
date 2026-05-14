# 工程实践

> 让代码"能跑起来"和"能长期维护、能协作交付"是两件事。这里沉淀的是后端工程师的"职业素养层"——设计模式、API 设计、Git、测试、Code Review、文档。

对应学习阶段：**贯穿全程**，建议在阶段 3（Web/RPC 服务开发）后开始系统积累。

---

## 📍 学习路径

```
阶段一：API 设计（接口是工程师的脸面）
  ├─ RESTful 设计原则与常见误区
  ├─ 资源建模与 URL 设计
  ├─ 错误码与错误响应规范
  ├─ 版本管理（URL / Header / Query）
  └─ 幂等、分页、批量、过滤的统一约定

阶段二：设计模式与代码组织（写出可演进的代码）
  ├─ 经典设计模式在 Go 里的"去 Java 化"实现
  ├─ 依赖注入与控制反转
  ├─ 分层架构（DDD-Lite / Clean Architecture）
  ├─ 包结构与依赖方向
  └─ 接口设计原则（SOLID 在 Go 中的取舍）

阶段三：测试体系（让代码可被信任）
  ├─ 单元测试的边界与价值
  ├─ Mock / Stub / Fake 的取舍
  ├─ 集成测试与 Testcontainers
  ├─ 覆盖率的真相与陷阱
  └─ Benchmark 与性能回归

阶段四：版本控制与协作（让团队不打架）
  ├─ Git 的对象模型（blob / tree / commit）
  ├─ rebase vs merge 的本质差异
  ├─ 分支模型（Git Flow / Trunk-Based / GitHub Flow）
  ├─ Commit Message 规范
  └─ 解决冲突的正确姿势

阶段五：协作与交付（让代码顺利落地）
  ├─ Code Review 的目标与边界
  ├─ 技术方案文档（RFC）怎么写
  ├─ API 文档与契约管理（OpenAPI / Protobuf IDL）
  ├─ 需求评审到上线的全流程
  └─ 重构的时机与策略
```

---

## 🎯 核心问题清单

> 标注：`[ ]` 待开始 / `[/]` 进行中 / `[x]` 已完成

### 阶段一：API 设计

- [ ] [RESTful 到底是什么以及它和 RPC 的本质区别](./RESTful到底是什么以及它和RPC的本质区别.md)
- [ ] [POST 和 PUT 和 PATCH 在 REST 里的语义边界是什么](./POST和PUT和PATCH在REST里的语义边界是什么.md)
- [ ] [URL 应该用动词还是名词以及嵌套资源该怎么设计](./URL应该用动词还是名词以及嵌套资源该怎么设计.md)
- [ ] [HTTP 状态码和业务错误码应该怎么搭配使用](./HTTP状态码和业务错误码应该怎么搭配使用.md)
- [ ] [API 版本管理放 URL 还是 Header 各有什么取舍](./API版本管理放URL还是Header各有什么取舍.md)
- [ ] [分页应该用 offset 还是 cursor](./分页应该用offset还是cursor.md)
- [ ] [批量接口的设计要点和常见反模式](./批量接口的设计要点和常见反模式.md)
- [ ] [幂等接口的设计原则和实现方式](./幂等接口的设计原则和实现方式.md)
- [ ] [接口应该返回包装结构还是裸数据](./接口应该返回包装结构还是裸数据.md)

### 阶段二：设计模式与代码组织

- [ ] [Go 里实现单例为什么不需要双重检查锁](./Go里实现单例为什么不需要双重检查锁.md)
- [ ] [工厂模式在 Go 里的常见落地形式](./工厂模式在Go里的常见落地形式.md)
- [ ] [策略模式和函数类型在 Go 里是怎么融合的](./策略模式和函数类型在Go里是怎么融合的.md)
- [ ] [装饰器模式和中间件的本质是同一回事吗](./装饰器模式和中间件的本质是同一回事吗.md)
- [ ] [Functional Options 模式解决了什么问题](./FunctionalOptions模式解决了什么问题.md)
- [ ] [依赖注入在 Go 里有哪些实现方式](./依赖注入在Go里有哪些实现方式.md)
- [ ] [SOLID 原则在 Go 里哪些适用哪些要变形](./SOLID原则在Go里哪些适用哪些要变形.md)
- [ ] [Go 项目的目录结构应该怎么组织](./Go项目的目录结构应该怎么组织.md)
- [ ] [internal 目录的作用和包依赖方向应该怎么管控](./internal目录的作用和包依赖方向应该怎么管控.md)
- [ ] [DDD 的分层在中小项目里值得引入吗](./DDD的分层在中小项目里值得引入吗.md)
- [ ] [充血模型和贫血模型在 Go 里怎么落地](./充血模型和贫血模型在Go里怎么落地.md)

### 阶段三：测试体系

- [ ] [单元测试到底应该测什么不应该测什么](./单元测试到底应该测什么不应该测什么.md)
- [ ] [Mock 和 Stub 和 Fake 的区别是什么](./Mock和Stub和Fake的区别是什么.md)
- [ ] [测试覆盖率高就一定代表代码质量好吗](./测试覆盖率高就一定代表代码质量好吗.md)
- [ ] [table-driven 测试为什么是 Go 的最佳实践](./table-driven测试为什么是Go的最佳实践.md)
- [ ] [集成测试用 Testcontainers 还是自建测试环境](./集成测试用Testcontainers还是自建测试环境.md)
- [ ] [Benchmark 的常见陷阱和如何避免被编译器优化掉](./Benchmark的常见陷阱和如何避免被编译器优化掉.md)
- [ ] [测试金字塔在后端服务里应该是什么形状](./测试金字塔在后端服务里应该是什么形状.md)

### 阶段四：版本控制与协作

- [ ] [Git 的 commit 和 tree 和 blob 三层对象到底是什么](./Git的commit和tree和blob三层对象到底是什么.md)
- [ ] [rebase 和 merge 的本质区别以及什么时候用哪个](./rebase和merge的本质区别以及什么时候用哪个.md)
- [ ] [git reset 的 soft mixed hard 三种模式分别在做什么](./git_reset的soft_mixed_hard三种模式分别在做什么.md)
- [ ] [git revert 和 git reset 的差异以及生产环境该用哪个](./git_revert和git_reset的差异以及生产环境该用哪个.md)
- [ ] [Cherry-pick 的使用场景和潜在风险](./Cherry-pick的使用场景和潜在风险.md)
- [ ] [Git Flow 和 Trunk-Based 和 GitHub Flow 各自适合什么团队](./GitFlow和TrunkBased和GitHubFlow各自适合什么团队.md)
- [ ] [Conventional Commits 规范到底解决了什么问题](./ConventionalCommits规范到底解决了什么问题.md)
- [ ] [merge 冲突的正确解决姿势以及怎么提前规避](./merge冲突的正确解决姿势以及怎么提前规避.md)
- [ ] [git stash 和 worktree 各自适合什么场景](./git_stash和worktree各自适合什么场景.md)

### 阶段五：协作与交付

- [ ] [Code Review 应该看什么以及不应该看什么](./CodeReview应该看什么以及不应该看什么.md)
- [ ] [一份合格的技术方案文档应该包含哪些章节](./一份合格的技术方案文档应该包含哪些章节.md)
- [ ] [OpenAPI 和 Protobuf IDL 在契约管理上各自的优势](./OpenAPI和ProtobufIDL在契约管理上各自的优势.md)
- [ ] [接口文档和代码不一致是怎么造成的怎么治理](./接口文档和代码不一致是怎么造成的怎么治理.md)
- [ ] [需求评审到上线的全流程都应该卡哪些点](./需求评审到上线的全流程都应该卡哪些点.md)
- [ ] [重构应该在什么时机做以及怎么避免越改越乱](./重构应该在什么时机做以及怎么避免越改越乱.md)
- [ ] [技术债的识别和偿还策略](./技术债的识别和偿还策略.md)

---

## 📊 学习进度

- 总问题数：43
- 已完成：0 ✅
- 进行中：0 🔄
- 待开始：43 ⏳

---

## 📚 推荐资源

### 书籍
- 《代码整洁之道》Robert C. Martin
- 《重构：改善既有代码的设计》Martin Fowler
- 《领域驱动设计》Eric Evans
- 《架构整洁之道》Robert C. Martin
- 《Google 软件工程》

### 在线资源
- [Pro Git 中文版](https://git-scm.com/book/zh/v2)
- [Conventional Commits](https://www.conventionalcommits.org/zh-hans/)
- [Google Engineering Practices](https://google.github.io/eng-practices/)
- [Go Project Layout](https://github.com/golang-standards/project-layout)
- [Effective Go](https://go.dev/doc/effective_go)
- [Uber Go Style Guide](https://github.com/uber-go/guide/blob/master/style.md)

---

## 📝 修订记录

- 2026-05-14：初版，列出 43 个核心问题，分 5 个阶段（API 设计 / 设计模式 / 测试 / Git / 协作交付）
