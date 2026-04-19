> 💡 代码改错了怎么办？刚才 commit / push 错了怎么救？`reset`、`revert`、`reflog` 到底该用哪个？

## 一、三种"撤销"的本质区别

| 命令 | 作用对象 | 是否改写历史 | 适用场景 |
|---|---|---|---|
| `git reset` | 移动 HEAD 指针 | ✅ 会改写 | **本地**未推送的提交 |
| `git revert` | 新建一个反向提交 | ❌ 不改写 | **已推送**的提交 |
| `git restore` | 工作区/暂存区文件 | ❌ 不涉及历史 | 还没 commit 的修改 |

> 口诀：**本地用 reset，线上用 revert，文件用 restore。**

## 二、撤销未提交的修改（restore）

```bash
git restore <file>                      # 放弃工作区修改
git restore --staged <file>             # 取消暂存（保留修改）
git restore --staged --worktree <file>  # 暂存 + 工作区一起放弃
```

## 三、撤销本地提交（reset）

```bash
git reset --soft HEAD^    # 撤销提交，修改回到暂存区（最温和）
git reset --mixed HEAD^   # 撤销提交和暂存，修改回到工作区（默认）
git reset --hard HEAD^    # 撤销提交并丢弃所有修改（⚠️ 危险）

git reset --hard <commit> # 彻底回退到指定提交
```

**三种模式的差别**：

| 模式 | HEAD | 暂存区 | 工作区 |
|---|---|---|---|
| `--soft` | 移动 | 保留 | 保留 |
| `--mixed`（默认） | 移动 | 清空 | 保留 |
| `--hard` | 移动 | 清空 | 清空 |

## 四、撤销已推送的提交（revert）

```bash
git revert <commit>           # 生成一个新提交来抵消指定提交的改动
git revert <c1>..<c2>         # 批量回滚一段区间
git revert -n <commit>        # 不自动提交（便于合并多次回滚）
```

> 为什么已推送的提交不能用 `reset`？因为 `reset` 会改写历史，其他人拉取时会产生冲突或被你的强推覆盖丢失工作。

## 五、找回"丢失"的提交（reflog）

> 只要还没被 gc 清理，任何 `reset --hard`、误删分支、rebase 翻车都能救回来。

```bash
git reflog                 # 查看 HEAD 的所有移动历史
git reset --hard <commit>  # 根据 reflog 里的哈希回到任意状态
```

**示例**：

```bash
$ git reflog
a1b2c3d HEAD@{0}: reset: moving to HEAD^
e4f5g6h HEAD@{1}: commit: 误删前的提交
# 想救回 e4f5g6h：
$ git reset --hard e4f5g6h
```

## 六、清理未追踪文件（clean）

```bash
git clean -n        # 预览将要删除什么（dry run，推荐先跑一次）
git clean -fd       # 强制删除未追踪的文件和目录
git clean -fdx      # 连 .gitignore 忽略的也删（慎用）
```

## 七、决策流程

```
要撤销的东西还没 commit？
  → git restore

已经 commit 但还没 push？
  → git reset（--soft 保暂存 / --mixed 保修改 / --hard 全丢）

已经 push 到远程？
  → git revert（生成反向提交，安全）

刚刚 reset --hard 后悔了？
  → git reflog 找回哈希 → git reset --hard <哈希>
```
