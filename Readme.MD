### git不常用命令

* 不知道为什么会出现这个问题 把http/https换成ssh
```shell
HTTP Basic: Access denied fatal: Authentication failed

git remote -v //git查看远程仓库地址命令
origin	http://code.paic.com.cn/scf/scf-web.git (fetch)
origin	http://code.paic.com.cn/scf/scf-web.git (push)

git remote set-url origin ssh://git@code.paic.com.cn:8002/scf/scf-web.git //修改http 为 ssh

git config --system --unset credential.helper //这个不知道是不是有用
```
* 新建仓库 连接远程仓库
```shell
git remote add origin git@github.com:zhonglinzha/git.git
git push -u origin master
```
* 用git命令拉取远端分支 其实使用客户端工具只是提高工作效率。
```shell
git fetch // 同步远程仓库
git checkout -b dev origin/dev // 拉取指定分支
git checkout -t origin/dev // 这个也可以
```

* git修改远程分支
```shell
git remote -v
git remote remove origin
git remote add origin
git push origin --all //修改仓库地址后，把所有分支一次性推送到远程
```

* git reset 三种模式
```shell
git reset --hard //这个操作一般不要用
git reset --mixed //这个默认 就是把commit回退到没有add的状态
git reset --soft //这个是把commit回退到add之后，没有commit的状态
git log
git reflog //找回历史
```
* git rm 删除文件
```shell
git rm fileName //删除文件，这个类似删除，工作取，暂存区，仓库都没有了
git rm --cached fileName // 这个会保留工作区，意思是你想把它加到.gitignore中
```
* git gerrit 联合使用（gerrit个人认为已经是上古时代的东西）
```shell
git  push origin HEAD:refs/for/dev
//git remote -v
//origin  git@github.com:zhonglinzha/git.git (fetch)
//origin  git@github.com:zhonglinzha/git.git (push)
// 这里解释一波：git push 中的origin 和 remote中的 origin 是对应的
// 也可以是别的 origin 一般是默认的

//gerrit git pull 容易丢失 Change-Id
//这里使用这个命令
git commit --amend

```
