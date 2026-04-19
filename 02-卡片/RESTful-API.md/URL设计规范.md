> 💡 URL 应该怎么写才符合 RESTful 风格？用名词还是动词？要不要用复数？

URL 的核心职责是**定位资源**，动作交给 HTTP Method 去表达。以下是常见的设计约定：

## 1. 用名词，不用动词
资源是名词，动作由 Method 承担，不要把动词塞进 URL。
```http
GET    /users          ✅
POST   /orders         ✅

GET    /getUsers       ❌
POST   /createOrder    ❌
```

## 2. 资源集合用复数
复数更符合"集合"的语义：`/users`、`/orders`、`/products`，而不是 `/user`、`/order`。

## 3. 层级不要过深
通过路径体现资源从属关系，但层级一般控制在 2~3 层内，过深时考虑独立建模。
```http
/users/1/orders              ✅ 用户下的订单集合
/users/1/orders/1001/items/3 ❌ 层级过深，可拆成 /order-items
```

## 4. 多单词命名风格统一
连字符和下划线都可以，**关键是全项目保持一致**，不要混用。
```http
/order-items   或   /order_items
```

## 5. 查询条件不写进路径
过滤、分页、排序、搜索等条件用查询参数表达，不要塞进路径语义里。
```http
GET /orders?status=paid&page=1&page_size=20        ✅
GET /getPaidOrdersByUserId/1/1/20                  ❌
```
