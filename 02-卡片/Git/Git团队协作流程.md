> 💡 团队协作中一个功能分支从拉代码到合并上线的标准流程是什么？为什么要用 `--no-ff` 合并、`--force-with-lease` 推送？

## 一、核心原则

- **主分支永远可发布**：`main` / `master` 上任何时刻的代码都应该是可上线的。
- **功能分支短命**：一个分支只做一件事，尽快合并，避免长期分叉。
- **历史线性可读**：通过 `rebase` 让个人开发历史保持线性，通过 `--no-ff` 让合并历史保留"功能单元"边界。
- **已推送的共享提交不要改写**：只对自己本地、未共享的提交做 rebase / amend。

## 二、标准工作流（七步）

```bash
# 1. 同步主分支
git switch main
git pull --rebase

# 2. 创建功能分支
git switch -c feature/xxx

# 3. 开发并小步提交
git add -p
git commit -m "feat: xxx"

# 4. 推送前同步主分支最新代码（保持线性）
git fetch origin
git rebase origin/main
# 若冲突：解决后 git add . && git rebase --continue

# 5. 推送
git push -u origin feature/xxx
# rebase 后再次推送需要：
git push --force-with-lease

# 6. 合并到主分支（MR/PR 或本地）
git switch main
git merge --no-ff feature/xxx
git push

# 7. 清理已合并分支
git branch -d feature/xxx
git push origin --delete feature/xxx
```

## 三、两个关键参数

### `--no-ff`（no fast-forward）合并

默认 `merge` 在能快进时会直接移动指针，**丢失"这是一次功能合并"的信息**。`--no-ff` 强制生成一个 merge commit：

```
*   Merge branch 'feature/login'   ← merge commit，保留功能边界
|\
| * feat: add form
| * feat: add api
|/
* main: previous
```

好处：回滚整个功能时只需 revert 这一个 merge commit；`git log --first-parent` 能看到清晰的功能列表。

### `--force-with-lease`（安全的强制推送）

`rebase` 会改写提交历史，再次推送时远程分支会拒绝，必须强推。但普通的 `-f` / `--force` 会**无条件覆盖**远程，可能冲掉同事刚推上去的提交。

`--force-with-lease` 只在"远程分支自上次拉取后没被别人动过"时才推送成功，否则拒绝。**rebase 后推送的默认选择**。

## 四、常见场景

| 场景 | 推荐做法 |
|---|---|
| 每天开工 | `git switch main && git pull --rebase` |
| 本地提交太碎想整理 | `git rebase -i` 后 `--force-with-lease` 推送 |
| 合并功能分支到主干 | `git merge --no-ff feature/xxx` |
| 热修复紧急 bug | 从 `main` 切 `hotfix/xxx`，修完合回 `main` 并打 tag |
| 发现主分支有 bug，但只想修一部分 | 在 hotfix 分支上 `cherry-pick` 对应提交 |
