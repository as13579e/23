## git常用操作命令

### 使用较多
* git status    查看仓库变更状态：
* git init   把当前目录变成一个git仓库
* git add .    把本地修改添加到暂存区
* git commit -m"备注"  把暂存区的修改提交到本地仓库
* git push origin develop:master   把本地仓库的develop分支推送到远程仓库的master分支,当本地分支和远程分支同名时，develop:master可以简写才分支名
* git pull origin master    拉取和合并  远程仓库的master分支到本地仓库的master分支
* git branch 分支名         创建分支
* git branch -a	查看所有分支
* git branch -D 分支名           强制删除本地分支，注意不能在该分支上删除该分支，要先切到其他分支
* git push origin --delete 分支名         删除远程分支
* git checkout 分支名         切换分支
* git remote add origin 项目https或ssh克隆地址               本地仓库关联远程仓库
* git clone 项目https或ssh克隆地址                 克隆远程仓库
* 本地版本回退              git reset --hard SHA  //SHA为某次提交的id
* 远程仓库本报回退          （1） git reset --hard SHA //先本地回退（2）git push -f //再强制推送
* 合并某个提交到当前分支          （1） git cherry-pick SHA


### 使用较少
* git config --global user.name "Your Name"      使用Git的第一件事就是设置你的名字和email
* git config --global user.email "email@example.com"        使用Git的第一件事就是设置你的名字和email
* git config -l     查看本地git用户名和邮箱
* git rm --cache <fileUrl>   撤销某个文件在暂存区的修改
* git fetch origin master    拉取  远程仓库的master分支的内容
* git merge origin master    合并  远程仓库的master分支到本地仓库的master分支
* git diff 文件名          查看文件修改内容
* git log      查看仓库提交日志 
* git reflog   查看仓库所有版本，一次提交一个版本 


### Git错误--git remote: HTTP Basic: Access denied
原因：本地git配置的用户名、密码与gitlabs上注册的用户名、密码不一致。

解决方案： 
1. 如果账号密码有变动 用这个命令` git config –system –unset credential.helper` 重新输入账号密码 应该就能解决了 
2. 如果用了第一个命令 还不能解决问题那么 用这个命令： `git config –global http.emptyAuth true`
3. 如果以上两个方法不起作用，那么采用以下方法：
>进入控制面板》用户账号》凭据管理器？windows凭据》普通凭据，在里面找到git，点开编辑密码，更新为最新密码之后就可以正常操作了。

* 使用npm命令来安装、升级、卸载各种包，而且后台走的还是淘宝镜像 `npm config set registry https://registry.npm.taobao.org` // 配置后可通过下面方式来验证是否成功 `npm config get registry`   //这里直接输出淘宝镜像的地址registry.npm.taobao.org

### 在提交代码前通过eslint验证代码
```
npm install husky -D -S

//int-staged
//使用 lint-staged 了。它只会校验检查你提交或者说你修改的部分内容。
npm install lint-staged -D -S
然后，修改 package.json 配置：

"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
},
"lint-staged": {
    "src/**/*.{js,vue}": [
      "eslint --fix",
      "git add"
    ]
  }
```
[Git Hooks](https://panjiachen.github.io/vue-element-admin-site/zh/guide/advanced/git-hook.html#husky)