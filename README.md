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
执行上述命令后，本地分支的代码就已经包含了对应的远程服务器分支feature/test中的代码了；此时如果有冲突，需要进行对应的冲突问题修正；
如果没有冲突的话，如果直接执行git push命令，则会报错；
（已经进行了本地分支和远程分支的关联： 
直接将本地分支代码提交到远程分支上，如果远程分支不存在，则直接创建同名远程分支：git push --set-upstream origin feature/task01
如果远程分支本身已经提前创建存在了，那么可以使用下面命令进行关联：git branch --set-upstream-to=origin/feature/task01
）
上述操作结束后，未避免其他问题，首先执行命令：git pull，同步本地代码和远程服务器代码，查看是否存在冲突；存在则解决后提交，并push到对应分支。
然后提交分支2代码到对应的远程分支2上；  
查看此刻分支2上面已经包含之前feature/test分支上面分支1提交的那部分代码及其他人员后续提交的代码信息。  
  
分支创建命令：  
git checkout -b feature/test  
git checkout -b feature/task01  
git checkout -b feature/task02  
git checkout -b feature/task03  
  
  
