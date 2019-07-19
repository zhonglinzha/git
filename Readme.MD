###git不常用命令

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