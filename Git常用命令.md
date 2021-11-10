## Git常用命令

1. 从远端克隆项目到本地：git clone 项目地址（克隆主分支上的代码）（这种方式前提是本地没有创建Git仓库）
2. git clone -b <指定分支名> <远程仓库地址>（克隆指定分支上的代码）
3. 在本地创建一个开发分支并与远端仓库的分支相关联：git checkout -b 本地分支名 origin 远端仓库分支名
4. 查看本地分支目录：git branch
5. 查看远程分支目录： git branch -a
6. 查看本地分支与远程分支的对应关系：git branch -vv
7. 切换本地分支：git switch 分支名
8. 融合子分支代码与主分支代码： git merge master / git merge dev / git merge --no-ff -m "merge with no-ff" dev（--no-ff 表示禁用 Fast forward 注意： 在 Fast forward 模式下删除分支后会丢掉分支信息）
9. 创建一个功能分支：git checkout -b 功能分支名（如：feature-x） 父分支名（通常是开发分支 develop)
10. 删除分支：git branch -d 分支名
11. 显示代码提交记录（从近到远）：git log / git log--pretty=oneline / git log --graph --pretty=oneline --abbrev-commit(查看分支合并情况)
12. 版本回退： get reset --hard HEAD^(仅仅返回上一个版本) / git reset --hard 版本号（可以使用git log查看版本号）
13. 列出已经存在的远程分支：git remote 
14. 已有本地分支与远程分支创建关联：git branch --set-upstream-to origin/远程分支名 本地分支名  
15. 取消本地分支与远端分支的关联：git branch --unset-upstream 本地分支名 
16. 推送本地分支代码到远程分支：git push origin HEAD:远程分支名
17. 拉取远程分支代码到本地：git pull origin 远程分支
18. 暂存本地不需要提交的代码：git stash push 需要暂存的代码路径，可多个 -m '描述'  
19. 将之前暂存的代码退回给工作区间：git stash pop 
20. 撤销之前某一次提交(普通的提交，即只有单独一个commit)： git revert  commit_id
21. 撤销之前某一次提交（存在merge commit）：git revert  commit_id -m 数字（数字从左往右依次为1，2，....）
22. 合并、压缩、修改已上库的commit：git rebase -i HEAD~1 (数字可自定义)
23. 拉取特定分支代码：git clone 远程仓库地址； git checkout -b 分支名 tag标签名

## 克隆远程库中部分文件夹到本地仓库

1. 在本地初始化一个git仓库：git init
2. 设置允许克隆子目录： git config core.sparsecheckout true
3. 设置要克隆的仓库的子目录路径：echo '子目录绝对路径' >> .git/info/sparse-checkout
4. 将本地的git仓库与远端仓库相关联： git remote add origin 仓库项目地址
5. git pull origin 分支  就可以将自己想要的库上部分项目代码拉到本地



##git使用常见问题

1. Git :fatal: refusing to merge unrelated histories解决

```
解决方法： git pull origin master --allow-unrelated-histories
```



