1) git 进入本地项目目录

dingyu@kedingyu MINGW64 ~/projects (master)
$ pwd
/c/Users/dingyu/projects

/*************************************
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