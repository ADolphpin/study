




------------------------------------------------------
------------------------------------------------------

1) git 本地配置 

第一步，检查 SSH keys的设置
首先我们需要检查你电脑上现有的 ssh key：

$ cd ~/.ssh 

检查本机的ssh密钥
如果提示：No such file or directory 说明你是第一次使用 git。

生成新的 SSH Key：
$ ssh-keygen -t rsa -C "邮件地址@youremail.com"

Generating public/private rsa key pair.
Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):<回车就好>
注意 1: 此处的邮箱地址，你可以输入自己的邮箱地址；
注意2: 此处的「-C」的是大写的「C」
然后系统会要你输入密码：

Enter passphrase (empty for no passphrase):<输入加密串>
Enter same passphrase again:<再次输入加密串>

第二步，添加 SSH Key 到 GitHub
在本机设置 SSH Key 之后，需要添加到 GitHub上，以完成 SSH 链接的设置。

1、打开本地 id_rsa.pub 文件（ 参考地址 C:\Documents and Settings\Administrator.ssh\id_rsa.pub）。此文件里面内容为刚才生成的密钥。如果看不到这个文件，你需要设置显示隐藏文件。准确的复制这个文件的内容，才能保证设置的成功。

2、登陆 GitHub 系统。点击右上角的 Account Settings—>SSH Public keys —> add another public keys

3、把你本地生成的密钥复制到里面（ key 文本框中）， 点击 add key 就ok了



$ git config --global user.name "Your Name"
//$ git config --global user.name "jiangmin"
$ git config --global user.email "email@example.com"
$ git config --global user.email "11082****@qq.com"


因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。
注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址


------------------------------------------------------
------------------------------------------------------


1) git 进入本地初始化项目目录

dingyu@kedingyu MINGW64 ~/projects (master)
$ pwd
/c/Users/dingyu/projects

/*************************************

$ git init
会生成一个隐藏的.git 目录
$ ls -ah
./  ../  .git/
****************************************/

2) 添加本地仓库

第一步，用命令git add告诉Git，把文件添加到仓库：
$ git add readme.txt
// $ git add [文件名](需要添加的文件名称)

第二步，用命令git commit告诉Git，把文件提交到仓库：
$ git commit -m "first test add a file"
//$ git commit -m "此处为提交时注释信息，比如做了什么修改"

3) 关联远程库提交

第一步，建立远程仓库：
$ git remote add origin git@github.com:ADolphpin/study.git
//$ git remote add origin git@github.com:[github账号]/[项目名称].git


// 如果输入有误，可以删除远程 Git 仓库
// $ git remote rm origin


第二步，关联后，使用命令：
git push -u origin master  
//第一次推送master分支的所有内容；


此后，每次本地提交后，只要有必要，就可以使用命令
git push origin master
推送最新修改；