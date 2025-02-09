# Git学习笔记

## 2024-01-29 学习内容

### 1. Git基本配置
# 设置用户名和邮箱
git config --global user.name "您的GitHub用户名"
git config --global user.email "您的GitHub邮箱"

# 验证配置
git config user.name
git config user.email

### 2. 创建和初始化仓库

# 创建新文件夹
mkdir my-first-git
cd my-first-git

# 初始化Git仓库
git init

### 3. 基本操作

# 查看状态
git status

# 添加文件到暂存区
git add test.txt

# 提交更改
git commit -m "提交说明"

# 查看提交历史
git log

### 4. 版本管理

# 查看特定版本
git checkout <commit-id>

# 返回最新版本
git checkout master

# 查看具体修改内容
git diff

### 5. GitHub操作

# 添加远程仓库
git remote add origin https://github.com/用户名/仓库名.git

# 推送到GitHub
git push -u origin master

# 后续推送（不需要-u参数）
git push origin master

### 6. 分支操作
# 查看所有分支
git branch

# 创建新分支
git branch feature-name

# 切换到指定分支
git checkout feature-name

# 创建并切换分支（组合命令）
git checkout -b feature-name

# 合并分支（先切换到目标分支）
git merge feature-name

# 删除分支
git branch -d feature-name

### 7. 实用技巧

# 暂存当前工作
git stash

# 恢复暂存的工作
git stash pop

# 查看暂存列表
git stash list

# 撤销未提交的修改
git restore 文件名

# 撤销已暂存的修改
git restore --staged 文件名

# 修改最后一次提交信息
git commit --amend

### 8. 团队协作

# 从远程拉取更新
git pull origin master

# 查看远程仓库信息
git remote -v

# 解决冲突
# 1. 手动修改冲突文件
# 2. git add 冲突文件
# 3. git commit 提交解决结果

### 9. .gitignore 文件使用
# 创建 .gitignore 文件
touch .gitignore

# 常用忽略规则：
# *.log    - 忽略所有 .log 文件
# node_modules/ - 忽略 node_modules 文件夹
# .env     - 忽略环境配置文件
# .DS_Store - 忽略 Mac 系统文件

### 10. 注意事项
1. 在 detached HEAD 状态（查看历史版本时）不要做修改
2. 使用 `git push -f` 要谨慎，因为会覆盖远程历史
3. 每次修改文件后的操作流程：
   - `git add` 添加到暂存区
   - `git commit` 提交修改
   - `git push` 推送到远程

### 11. Commit Message 规范
格式：<type>: <subject>

常用type：
- feat: 新功能
- fix: 修复bug
- docs: 文档更新
- style: 代码格式修改
- refactor: 重构代码
- test: 测试相关
- chore: 构建过程或辅助工具的变动

示例：
git commit -m "feat: 添加用户登录功能"
git commit -m "fix: 修复登录验证bug"

### 12. 常见问题解决
1. 提交错误：
   - 撤销最后一次提交：git reset HEAD~1
   - 强制推送：git push -f（谨慎使用）

2. 分支错误：
   - 切换分支前先提交或暂存更改
   - 误删分支可用：git reflog 查看历史

3. 冲突处理：
   - 先pull最新代码
   - 解决冲突
   - 提交解决结果