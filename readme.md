### git常用操作命令
* git status：查看仓库变更状态：
* git init：把当前目录变成一个git仓库
* git add .把本地修改添加到暂存区
* git rm --cache <fileUrl>：撤销某个文件在暂存区的修改
* git commit -m"备注"  把暂存区的修改提交到本地仓库
* git push origin master：把本地仓库的master分支推送到远程仓库的master分支
* git pull origin master：拉取和合并远程仓库的master分支到本地仓库的master分支
* git branch 分支名    ：创建分支
* git checkout 分支名    ：切换分支

* 本地版本回退：git reset --hard SHA  //SHA为某次提交的id
* 远程仓库本报回退：（1） git reset --hard SHA //先本地回退（2）git push -f //再强制推送
* 合并某个提交到当前分支：（1） git cherry-pick SHA

develop
master
2
