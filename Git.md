# 第一板块:Git

## Git常用命令:

1.git config --global user.name "用户名"  **//创建用户名**

2.git congif --global user.email "邮箱地址"  **//创建用户邮箱**

3.git init  **//初始化本地库**

4.git status  ***//查看本地库状态***

5.git add "文件名"  **//将文件上传到暂存区**

6.git commit -m"日志信息" 文件名  **//提交本地库**

7.git reflog  **//查看版本信息**

8.git reset --hard 版本号  **//版本穿梭**

## 初始化本地库:

​	如果要用Git管理本地库,那么要先在要管理的文件夹里按shift+右键打开Git Bash Here,然后初始化本地库,也就是**git init**,Git便会在当前管理的文件夹内创建一个.git文件夹;在这之后可以通过在Git里ll查看.git(注意.git文件默认是隐藏文件,若要查看可以输入"ll -a").

## 查看本地库状态:

​	在git里输入"git status"以查看本地库状态,会显示日志,其中第一行显示的是**当前本地库所在的分支**(例如:On branch master,意思是当前本地库在分支master上);第二行会显示**当前本地库有无提 文件并上传:

## 在本地库中创建和删除文件并上传:

​	以创建hello.txt为例子: 首先在Git里输入"**vim** hello.txt",接着就会进入到即将要创建的hello.txt中,再输入完内容后**按esc推出编辑模式**,输入"**:wq**"进行**保存**,这边完成了一个txt文档的创建.	但是创建完的文件也仅存在于工作区,通过git status可以看到此时的hello.txt是**标红**的,说明**还未进入暂存区**,此时可以**git add** hello.txt来将txt文档上传到暂存区(之后git status可以看到hello.txt变为**绿色**).	若要删除hello.txt文件(删除存在于**暂存区**里的hello.txt,**工作区内的仍然存在**),需输入"**git rm** --cached hello.txt"进行**删除**.

## 提交本地库:

​	**基本语法**是**git commit -m "日志信息" 文件名**.例如要将hello.txt所在的本地库提交(要先将hello.txt上传至暂存区),则输入git commit -m "first commit" hello.txt![image-20250115184530340](C:\Users\Akinass\AppData\Roaming\Typora\typora-user-images\image-20250115184530340.png)

需要注意的是图中7位字符串"**601a897**"是这一次提交的**版本号**(完整版本号的前七位). 此时可以**git reflog**来**查看引用日志信息**,如下图所示.当然,用**git log**也可**查看详细的版本信息**.![image-20250115184945574](C:\Users\Akinass\AppData\Roaming\Typora\typora-user-images\image-20250115184945574.png)

## 修改文件:

​	修改文件也是通过vim 文件名进行,例如要修改hello.txt,则需要vim hello.txt.修改后的hello.txt文件在git status中会**被标红**(没有被添加至暂存区),说明该文件被修改.

## 版本穿梭:

​	若想回到之前编辑过的版本,可以通过git reset --hard 版本号来实现,例如git reset --hard 601a897可以穿梭到版本号为601a897的版本.

## 分支的操作:

1.git branch 分支名  **//创建分支**

2.git branch -v  **//查看分支**

3.git checkout 分支名  **//切换分支**

4.git merge 分支名  **//把指定的分支合并到当前分支上**

## 合并分支时的注意事项:

​	如果在同一行修改了代码,而且想要将分支合并,那么Git会报错.此时**需要人为的编辑**,需要注意的是人为编辑之后再git commit时"日志信息"后**不应加上文件名**.

## Git团队协作机制:

1.团队内协作

2.跨团队协作4

## 远程仓库操作:

1.git remote -v  **//查看当前所有远程地址别名**

2.git remote add 别名 远程地址  **//起别名**

3.git push 别名 分支  **//推送本地分支上的内容到远程仓库**

4.git clone 远程地址  **//将远程仓库的内容克隆到本地**

5.git pull 远程库地址别名 远程分支名  **//将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并**



