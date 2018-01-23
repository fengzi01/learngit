工作空间 => 暂存区 => 本地库

工作目录——>暂缓区，使用git add命令（添加）
暂缓区——>版本仓库，使用git commit命令（确认）
工作目录——>版本仓库，使用git commit -am命令

git diff  工作空间 <=> 缓存区
git diff --cached 缓存区 <=> 本地库

git reset HEAD file --> 可以把暂存区的修改撤销掉（unstage），重新放回工作区

git checkout -b dev  --> 命令加上-b参数表示创建并切换

git checkout master  --> 切换分支
