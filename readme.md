### git常用操作命令
* git add .把本地修改添加到暂存区
* git commit -m"备注"  把暂存区的修改提交到本地仓库
* git push origin master  把本地仓库的当前分支推送到远程仓库的master分支
* git push  上传本地所有分支代码到远程对应的分支上。
* 本地版本回退：git reset --hard SHA  //SHA为某次提交的id
* 远程仓库本报回退：（1） git reset --hard SHA //先本地回退（2）git push -f //再强制推送
* 合并某个提交到当前分支：（1） git cherry-pick SHA
1