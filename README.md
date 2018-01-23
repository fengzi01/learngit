工作空间 => 暂存区 => 本地库

工作目录——>暂缓区，使用git add命令（添加）
暂缓区——>版本仓库，使用git commit命令（确认）
工作目录——>版本仓库，使用git commit -am命令

git diff  工作空间 <=> 缓存区
git diff --cached 缓存区 <=> 本地库

git reset HEAD file --> 可以把暂存区的修改撤销掉（unstage），重新放回工作区

git checkout -b dev  --> 命令加上-b参数表示创建并切换
git checkout master  --> 切换分支
git branch --> 列出分支
git branch -d branch_name --> 删除branch分支
git merge dev 合并分支

## branch merge操作
git add readme.txt
git commit -m 'modify readme'
git checkout master
git merge --no-ff -m "merge with no-ff" dev  (--no-ff 非快速模式，因为本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去。)
git branch -d dev

## branch log
git log 
git show 
git reset --hard HEAD^
git reflog

git log --graph --pretty=oneline --abbrev-commit

## 远程操作
git remote add origin(别名，根据爱好命名) git@github.com:bukas/bukas.git
git push -u origin master --> 用户关联origin master分支与本地master分支

git checkout -b branch-name origin/branch-name
git branch --set-upstream branch-name origin/branch-name

## git stash
git stash

git checkout master
git checkout -b issue-101

git add readme.md
git commit -m "fix bug 101"

git checkout master
git merge --no-ff -m "merged bug fix 101" issue-101

git checkout dev
git stash pop

## tag
git tag -a v0.5 -m "signed version 0.5 released" fec145a
git tag -s v0.5 -m "signed version 0.5 released" fec145a

git push origin v1.0
git push origin --tags

## 别名
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.br branch
git config --global alias.unstage 'reset HEAD'
git config --global alias.last 'log -1'

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
