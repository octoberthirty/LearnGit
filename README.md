# LearnGit
学习git使用
chrome-error://chromewebdata

-git有好几个区，工作区（workspace）、暂存区（index）、本地仓库（local repository）、还有远程仓库（remote repository）。
-远程仓库为我们保存一份代码，如github，而工作区、暂存区和本地仓库都在本地；
-这也就是为什么我们在没有网络的环境下也能使用git提交（commit）代码，因为提交仅仅是提交到本地仓库中，待有网络之后在推送（push）到远程仓库。



一、克隆项目,终端输入
将项目从远程仓库拉到本地的工作区钟
git clone git@github.com:wenmobo/LearnGit.git

二、本地代码更新到远程仓库

1、把我们要提交的文件的信息添加到**暂存区**中。（.代表提交所有文件）

**git add .**


2、将暂存区中的文件提交到本地仓库中

（1）git commit -m "提交的描述信息"

（2）git commit - a -m "提交的描述信息"

这个方法就是可以把tracked的文件提交到本地仓库，就算这件没有git add，也能提交。这个就是省略了git add这一步。

3、将本地仓库的文件push到远程仓库
git push <远程主机名> <本地分支名> : <远程分支名>

<--注意，分支推送顺序的写法是<来源地>:<目的地>，所以git pull是<远程分支>:<本地分支>，而git push是<本地分支>:<远程分支>。--->

3.1 git push origin master

如果省略远程分支名，则表示将本地分支推送与之存在”追踪关系”的远程分支(通常两者同名)，如果该远程分支不存在，则会被新建。
上面命令表示，将本地的master分支推送到origin主机的master分支。如果后者不存在，则会被新建。


3.2 git push origin :master 

如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支，等同于 git push origin --delete master


三、git pull <远程分支>:<本地分支>
git pull是拉取远程分支更新到本地仓库的操作

