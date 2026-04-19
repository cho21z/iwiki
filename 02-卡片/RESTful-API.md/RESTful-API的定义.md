> 💡 什么是 RESTful API？它和普通的 Web 接口有什么区别？

RESTful API 是一种围绕 **“资源（Resource）”** 来设计 Web 接口的风格，它让 API 更符合 HTTP 协议本身的设计方式，也让系统更容易理解、扩展和维护。

## REST
REST 的全称是 **Representational State Transfer**，通常翻译为 **表述性状态转移**。落到工程实践里，它关注的是 **“资源”** 以及 **“如何通过统一的方式操作资源”**，而不是“动作”。

## 一个最直观的对比
不太 RESTful 的写法：
```http
POST /createUser
POST /deleteUser
GET  /getUserById?id=1
```
RESTful 风格更倾向于：
```http
POST   /users
GET    /users/1
DELETE /users/1
```
后者 URL 表示 **资源是什么**，而不是 **打算做什么动作**，动作交给 HTTP 方法表达。

## 不是“机械套模板”
RESTful 是一种 **设计思想**，不是接口命名技巧，是在语义清晰、风格统一的前提下去思考接口。
