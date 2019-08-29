# feature-push-demo
演示git多人协作开发分支代码提交规避冲突方法
1.创建属于不同开发人员自己的本地分支
分支1:feature/task01
分支2:feature/task02
分支3:feature/task03
2.分别在3个分支上创建不同的文件，并提交到自己对应的服务器分支代码上
名字分别为demo01.txt，demo02.txt和demo03.txt
3.创建用户合并不同开发人员的分支代码请求合并分支：freature/test
4.当分支1进行提交到自己对应的服务器远程分支后，用分支feature/test进行合并对应的变更信息；
然后切换到分支2上面，在提交分支2的代码前，执行同步分支代码命令，如下：
git pull --rebase origin feature/test
然后提交分支2代码到对应的远程分支2上；
查看此刻分支2上面是否包含之前分支1提交的那部分代码信息

分支创建命令：
git checkout -b feature/test
git checkout -b feature/task01
git checkout -b feature/task02
git checkout -b feature/task03


