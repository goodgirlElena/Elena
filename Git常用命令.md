## Git常用命令

1. 从远端克隆项目到本地：git clone 项目地址
2. 在本地创建一个开发分支并与远端仓库的分支相关联：git checkout -b 本地分支名 origin 远端仓库分支名
3. 查看本地分支目录：git branch
4. 切换本地分支：git switch 分支名
5. 融合子分支代码与主分支代码： git merge master / git merge dev / git merge --no-ff -m "merge with no-ff" dev（--no-ff 表示禁用 Fast forward 注意： 在 Fast forward 模式下删除分支后会丢掉分支信息）
6. 显示代码提交记录（从近到远）：git log / git log --pretty=oneline / git log --graph --pretty=oneline --abbrev-commit(查看分支合并情况)
7. 版本回退： get reset --hard HEAD^(仅仅返回上一个版本) / git reset --hard 版本号（可以使用git log查看版本号）
8. 列出已经存在的远程分支：git remote 

