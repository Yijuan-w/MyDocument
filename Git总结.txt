# Git总结

分布式版本控制系统
安装git，官网，注意路径中没有中文。

## 1. 用户名和密码

bio217@DESKTOP-G7HE4K2 MINGW64 ~ (master)

$ git config user.name

WYJ

bio217@DESKTOP-G7HE4K2 MINGW64 ~ (master)

$ git config user.email

wangyijuan@mail.sdu.edu.cn

修改用户名

git config --global user.name "xxxx(新的用户名)"

修改密码

git config --global user.password "xxxx(新的密码)"

修改邮箱

git config --global user.email "xxxx@xxx.com(新的邮箱)"

***
工作区：就是你在电脑里能看到的目录。

暂存区：英文叫 stage 或 index。一般存放在 .git 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。

版本库：工作区有一个隐藏目录 .git，这个不算工作区，而是 Git 的版本库。

git init 初始化一个git仓库

git add 文件名 添加文件

git commit -m"提交命令的说明" 将暂存区提交到本地仓库

git log -- oneline 查看历史版本

其他常见命令

https://www.runoob.com/git/git-basic-operations.html

廖雪峰
https://www.liaoxuefeng.com/wiki/896043488029600/897013573512192


一般工作流程如下：

克隆 Git 资源作为工作目录。
在克隆的资源上添加或修改文件。
如果其他人修改了，你可以更新资源。
在提交前查看修改。
提交修改。
在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

#git命令必须在git仓库下进行，添加文件时该文件必须在目录下
#git everything up-to-date 写之前commit git commit -m"msg"

## 2. ssh key
是否存在

ls

没有的话生成

ssh-kengen -t rsa -C"邮箱"

获取ssh key

cat id-rsa.pub 这个是公钥

去GitHub setting中设置

检查是否成功配置ssh

ssh -T git@github.com

#之前已经是http的链接的话，可以直接修改项目目录下.git文件夹下的config文件，从GitHub那里复制ssh

## 3. http连接
不稳定，各种问题，代理什么的

https://blog.csdn.net/qq_41775886/article/details/113688405

443 关代理

10054 git config --global http.sslVerify "false"

https://blog.csdn.net/weixin_43945983/article/details/110882074

关了那个验证之后多push几遍，看网络状况了

## 4. github/gitee and vscode
两种协议，非常详细的教程
M标识修改 +提交到缓存区
https://blog.csdn.net/qq_38981614/article/details/115013188

## 5. git http和ssh的区别
git中https和SSH的clone方式区别
https://www.jianshu.com/p/2cced982009f

在git中clone项目有两种方式：HTTPS和SSH，它们的区别如下：

HTTPS：不管是谁，拿到url随便clone，但是在push的时候需要验证用户名和密码；

SSH：clone的项目你必须是拥有者或者管理员，而且需要在clone前添加SSH Key。SSH 在push的时候，是不需要输入用户名的，如果配置SSH key的时候设置了密码，则需要输入密码的，否则直接是不需要输入密码的。


http token的问题

https://blog.csdn.net/weixin_41010198/article/details/119698015