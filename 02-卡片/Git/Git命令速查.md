> 参考：[Git Official Cheat Sheet](https://git-scm.com/cheat-sheet) 

## 一、配置 

```bash
# 全局用户信息（首次使用必配）
git config --global user.name "姓名"
git config --global user.email "邮箱"

# 仅对当前仓库生效（覆盖全局）
git config user.email "work@example.com"

# 查看配置
git config --list                    # 所有配置
git config --global --list           # 全局配置
git config user.name                 # 查看某一项

# 常用配置
git config --global core.editor "vim"           # 默认编辑器
git config --global pull.rebase true            # pull 时默认用 rebase（推荐）
git config --global init.defaultBranch main     # 默认分支名
git config --global core.autocrlf input         # 换行符处理（Mac/Linux）
```

## 二、创建仓库

```bash
git init                      # 在当前目录初始化仓库
git clone <url>               # 克隆远程仓库
git clone <url> <dir>         # 克隆到指定目录
```

## 三、日常提交

```bash
# 查看状态 / 差异
git status                    # 查看工作区状态
git diff                      # 工作区 vs 暂存区
git diff --cached             # 暂存区 vs HEAD（即将提交的内容）
git diff HEAD                 # 工作区 + 暂存区 vs HEAD（全部未提交的差异）
git diff <commit1> <commit2>  # 对比两次提交
git diff --stat               # 只看摘要（修改了哪些文件、行数）

# 暂存
git add <file>                # 暂存指定文件
git add .                     # 暂存当前目录下所有变更
git add -p                    # 交互式暂存（逐块选择，强烈推荐 code review 前使用）
git add -u                    # 只暂存已追踪文件的修改（不包含新文件）

# 取消暂存 / 放弃修改
git restore --staged <file>   # 取消暂存（新版推荐）
git restore <file>            # 放弃工作区修改（新版推荐）
git restore --staged --worktree <file>  # 同时放弃暂存和工作区修改

# 文件操作
git rm <file>                 # 从 git 和工作区删除
git rm --cached <file>        # 只从 git 移除，本地保留（常用于误提交的配置文件）
git mv <old> <new>            # 重命名/移动

# 提交
git commit -m "msg"           # 提交已暂存内容
git commit -am "msg"          # 暂存 + 提交（仅对已追踪文件）
git commit --amend            # 修改最近一次提交（信息或内容）
git commit --amend --no-edit  # 追加到上次提交但不改信息
```

## 四、分支管理

```bash
# 查看
git branch                    # 本地分支
git branch -a                 # 所有分支（含远程）
git branch -vv                # 带上游追踪和最近提交信息
git branch --merged           # 已合并到当前分支的分支（清理用）

# 创建 / 切换
git switch <branch>           # 切换分支（新版推荐）
git switch -c <branch>        # 创建并切换
git switch -c <branch> <commit>   # 从指定提交创建分支

# 删除
git branch -d <branch>        # 删除已合并的分支
git branch -D <branch>        # 强制删除
git push origin --delete <branch>   # 删除远程分支

# 合并
git merge <branch>            # 合并指定分支到当前分支
git merge --no-ff <branch>    # 保留分支历史（推荐团队协作）
git merge --abort             # 合并冲突时放弃本次合并

# 变基（rebase）—— 保持提交历史线性
git rebase <branch>           # 当前分支基于 branch 变基
git rebase --continue         # 解决冲突后继续
git rebase --abort            # 放弃变基
git rebase -i HEAD~3          # 交互式变基（合并/重写最近 3 次提交）
```

## 五、暂存与恢复

```bash
git stash                     # 暂存当前修改（切分支前救急）
git stash -u                  # 包含未追踪文件
git stash push -m "msg"       # 带备注暂存
git stash list                # 查看暂存列表
git stash pop                 # 恢复最近一次并删除 stash
git stash apply               # 恢复但保留 stash
git stash apply stash@{2}     # 恢复指定 stash
git stash drop stash@{0}      # 删除指定 stash
git stash clear               # 清空所有 stash
```

## 六、远程协作

```bash
# 远程仓库管理
git remote -v                          # 查看远程仓库
git remote add origin <url>            # 添加远程仓库

# 拉取 / 推送
git fetch                     # 拉取远程更新（不合并）
git fetch -p                  # 同时清理已删除的远程分支
git pull                      # fetch + merge
git pull --rebase             # fetch + rebase（推荐，保持历史整洁）

git push                      # 推送到上游分支
git push -u origin <branch>   # 首次推送并建立追踪关系
git push --force-with-lease   # 安全的强制推送（rebase 后必用，比 -f 更安全）
```

## 七、历史查看

```bash
# 提交日志
git log                       # 完整日志
git log --oneline             # 每条一行
git log --graph --oneline --all --decorate   # 图形化查看全部分支（强烈推荐）
git log -n 5                  # 最近 5 条
git log --author="张三"        # 按作者过滤
git log --since="2 weeks ago" # 按时间过滤
git log <file>                # 某文件的提交历史
git log --follow <file>       # 包含重命名之前的历史
git log -p <file>             # 显示每次提交的具体内容

# 查看具体提交
git show <commit>             # 查看某次提交详情
git show <commit> --stat      # 只看文件变更摘要
git show <commit>:<file>      # 查看某提交时该文件的内容

# 追溯
git blame <file>              # 每一行是谁、何时提交的
git reflog                    # 所有 HEAD 变更记录（救命神器）
```

## 八、撤销与回退

```bash
# 撤销提交（保留修改）
git reset HEAD^               # 撤销最近一次提交，修改回到工作区
git reset --soft HEAD^        # 撤销提交，修改回到暂存区
git reset --mixed HEAD^       # 撤销提交和暂存（默认）
git reset --hard HEAD^        # 撤销提交并丢弃修改（危险！）

# 回退到指定提交
git reset --hard <commit>     # 彻底回退（会丢失之后的提交）
git revert <commit>           # 新建一个反向提交来撤销（推荐用于已推送的提交）

# 清理
git clean -n                  # 预览将要删除的未追踪文件
git clean -fd                 # 强制删除未追踪的文件和目录
```

## 九、救急与进阶

```bash
# Cherry-pick：摘取其他分支的某次提交
git cherry-pick <commit>
git cherry-pick <commit1>..<commit2>   # 范围摘取

# 找回丢失的提交（reset --hard 后不要慌）
git reflog                    # 找到操作记录
git reset --hard <commit>     # 回到之前的状态

# 查找修改了特定文本的提交
git log -S "关键字"            # 查找代码中出现/消失过某字符串的提交
git log --grep="bugfix"       # 按 commit message 搜索
```

## 十、团队协作标准流程

```bash
# 1. 每天开工前同步代码
git switch main
git pull --rebase

# 2. 创建功能分支
git switch -c feature/xxx

# 3. 开发并提交（小步提交）
git add -p
git commit -m "feat: xxx"

# 4. 推送前同步主分支最新代码（保持线性历史）
git fetch origin
git rebase origin/main
# 如有冲突：解决后 git add . && git rebase --continue

# 5. 推送
git push -u origin feature/xxx
# 若 rebase 后需要再推送：
git push --force-with-lease

# 6. 合并到主分支（通过 MR/PR 或本地合并）
git switch main
git merge --no-ff feature/xxx
git push

# 7. 清理已合并的分支
git branch -d feature/xxx
git push origin --delete feature/xxx
```
