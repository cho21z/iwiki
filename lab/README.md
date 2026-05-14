# 动手实验

用于存放验证性实验、demo、benchmark 等。

## 适合放在这里的内容

- 验证某个知识点的小实验
- 性能对比 benchmark
- 框架 / 工具的 hello world
- 复现某个 bug 或行为的最小代码

## 命名建议

实验类文件可以用英文短描述命名（因为通常是代码文件而非 Markdown）：

```
lab/
├── goroutine-leak-demo/
├── redis-pipeline-bench/
├── grpc-interceptor-example/
└── kafka-consumer-rebalance/
```

目录内放代码 + 一个简短的 README 说明实验目的和结论即可。
