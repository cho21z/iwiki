> 💡 怎么把杂乱的提交历史整理成线性、干净的样子？想把最近几次提交合并/改写怎么办？只想把某个功能的部分改动提交上去怎么办？想把别的分支的某一次提交搬到当前分支怎么办？

## 一、为什么需要"变基与交互式操作"

日常 `git commit` 只是**记录**，而以下场景需要**重写/重组**历史：

- 功能分支开发多天，期间主分支已前进 → 想保持线性历史 → `git rebase`
- 一次修改包含多个逻辑（bug 修复 + 格式调整）→ 想拆成多个独立提交 → `git add -p`
- 最近 3 次提交有错字、顺序乱、可合并 → 想整理后再推送 → `git rebase -i`
- 另一个分支的某个 commit 很有用，但不想合并整个分支 → `git cherry-pick`

> ⚠️ 核心原则：**已推送到远程、且他人可能已基于它工作的提交，不要重写历史**。变基与交互式操作几乎只用于"本地尚未推送"或"个人功能分支"。

## 二、rebase：把分支"嫁接"到新基点

```bash
# 当前分支基于 target 分支变基
git rebase <target>
git rebase origin/main        # 最常见：把功能分支 rebase 到主分支最新

# 冲突处理
git rebase --continue         # 解决冲突、git add 后继续
git rebase --skip             # 跳过当前这次提交
git rebase --abort            # 放弃本次变基，回到开始前
```

**rebase vs merge 的直观区别**：

```
merge:  A---B---C---M       ← 保留分叉，产生合并提交
             \     /
              D---E

rebase: A---B---C---D'---E'  ← 线性历史，D/E 被"复制"到新基点
```

## 三、交互式变基 `rebase -i`：历史整容术

```bash
git rebase -i HEAD~3          # 整理最近 3 次提交
git rebase -i <commit>        # 整理到某个提交之后的所有提交
```

打开编辑器后，每行前的动作关键字：

| 关键字 | 作用 |
|---|---|
| `pick` | 保留该提交（默认） |
| `reword` | 保留代码，修改 commit message |
| `edit` | 暂停在此提交，允许修改代码后 `--continue` |
| `squash` | 合并到上一个提交，**保留**两者的 message |
| `fixup` | 合并到上一个提交，**丢弃**本次 message（最常用） |
| `drop` | 直接丢弃该提交 |

典型场景：把"修复拼写"、"补充注释"这类零碎提交 `fixup` 到主提交里，推送前只留下清晰的功能提交。

## 四、交互式暂存 `add -p`：提交粒度控制

```bash
git add -p <file>             # 逐"块"（hunk）选择性暂存
git add -p                    # 对所有变更逐块确认
```

每个 hunk 会询问动作，常用：

| 按键 | 含义 |
|---|---|
| `y` | 暂存这一块 |
| `n` | 不暂存 |
| `s` | 把大块拆成更小的块（split） |
| `e` | 手动编辑要暂存的行（最精细） |
| `q` | 退出 |

**典型用途**：一次改动里既有"新功能"也有"顺手格式化"，用 `add -p` 把它们拆成两个独立提交，code review 时会轻松很多。

> 对应的还有 `git checkout -p` / `git restore -p` / `git reset -p`，语义都是"按块操作"。

## 五、cherry-pick：精准搬运提交

```bash
git cherry-pick <commit>                # 把某个提交应用到当前分支
git cherry-pick <c1> <c2>               # 一次多个（逐个应用）
git cherry-pick <c1>..<c2>              # 区间（不含 c1，含 c2）
git cherry-pick <c1>^..<c2>             # 区间（含 c1，含 c2）

git cherry-pick --continue              # 冲突解决后继续
git cherry-pick --abort                 # 放弃
```

**典型用途**：

- hotfix 分支修了一个 bug，想同时带到 `main` 和 `release/*`
- 某个同事的实验分支里有一次很棒的提交，不想合并整个分支

## 六、场景速查

| 场景 | 推荐操作 |
|---|---|
| 功能分支过时，想同步主分支最新代码 | `git fetch && git rebase origin/main` |
| 最近几次提交想整理（合并/改 message/删除） | `git rebase -i HEAD~N` |
| 一次改动想拆成多个提交 | `git add -p` 分多次 `git commit` |
| 只想要别的分支的某一次提交 | `git cherry-pick <commit>` |
| rebase 时冲突，想彻底放弃 | `git rebase --abort` |
| rebase 后推送被拒 | `git push --force-with-lease`（见 [[Git团队协作流程]]） |
