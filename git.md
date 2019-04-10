##### 生成SSH（github或gitlab免密登录的过程）

1. 如果当前电脑从未生成过秘钥，要执行
    ssh-keygen -t rsa
    生成秘钥
2. 在用户根目录下面的.ssh文件夹中找到生成密钥，id_rsa.pub就是我们需要的公钥文件，复制里面所有的内容
3. 打开github/gitlab页面
4. 点击自己头像 选择下面的settings
5. 进入到settings页面之后左边栏中会有一个 ssh and gpg keys ，点击
6. 进入到ssh and gpg keys页面之后，页面的右上角会有一个 New SSH Key 的按钮， 点击
7. title文本框中选择性（可写可不写）的输入内容
8. 在key文本框中，粘贴刚才复制的公钥的全部内容
9. 点击下面的的 Add SSH Key 按钮
10. 获取或者push项目的时候，一定要记得选择ssh连接，才可以实现免密登录


##### git的基本使用

0. git的配置命令，这个命令只需要在一台电脑上只需要执行一次
    git config --global user.name xxx
    git config --global user.email xxx@xxx.xxx

1. git init（一个项目只需执行一次）
    git init命令，是将当前所在的文件夹，用git版本控制工具进行管理
    执行这句命令之后，会在当前文件夹中生成一个.git的隐藏文件夹，该文件夹就是git用来存储每次修改的历史记录的版本仓库

2. git clone 远程仓库的地址 本地文件夹名称(需要存放代码的文件夹)
    从远程仓库获取版本库到本地仓库
    本地文件夹名称可以不写，git会默认创建和远程仓库一样的名称

3. git remote
    展示所有的别名
    注意：如果当前项目是通过git clone从远程仓库获取下来的，那么会有一个默认的远程地址的别名（origin），指向的就是clone这个项目的远程地址

4. git remote -v 
    展示所有的别名对应的仓库地址

5. git remote add  别名  远程地址
    自定义远程地址的别名

6. git remote rm  别名
    删除别名

7. git pull 远程仓库地址 分支名称
    从远程仓库获取更新的内容

8. git pull --rebase 远程仓库地址 分支名称
    更新当前分支，协同开发时，用此命令更新当前分支

9. git branch 
    查看当前分支

10. git branch -d  分支名
    删除指定分支

11. git checkout -b  分支名
    创建并切换分支

12.  git checkout   分支名
    切换到指定分支 (先提交再切换)

13. git status 
    用来查看当前文件夹中，这些文件的状态，如果文件没有被git管理，会有 	untracked files 提示

14. git add . 
    用来将文件添加到git中，让git进行管理！（将文件添加到暂存区）

15. git commit -m "提示信息"  （将暂存区的文件提交到版本库生成新的版本）
    将当前的文件状态保存一份到版本库当中，生成一个新的版本，历史记录中会有这个版本的记录

16. git commit -am "提示信息"  
    git add . 和 git commit 的结合体

17. git log
    用来查看所有已经保存和提交的版本的内容

18. git reset --hard 版本号
    将代码恢复到指定的版本，通过git log查看版本号

19. git checkout 文件名
    将暂存区的文件恢复到工作目录

20. git checkout .
    将所有文件恢复为更改之前的状态

21. git push 远程仓库的地址/远程仓库别名 分支名称
    将本地仓库推送到远程仓库中

22. git stash 
    将代码放入暂存区，只会存放更改的文件，不会存放新增的文件

23. git stash pop
    将暂存区最近一次的代码放出来，并删除暂存区里面对应的代码

24. 原则：一般需要向远程仓库推送新内容之前，需要先获取一次最新的代码

25. 执行push之前需要先执行一次pull操作

26. git merge 分支名
    将指定分支合并到当前分支

27. git merge --abort
    当merge出问题时，退出当前merge

28. git push 远程仓库地址 分支名称 --force
    强制提交   注意：千万不要用这个方法提交，会将别人已经修改的代码清空！！！

