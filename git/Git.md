本地仓库基本操作：
```bash
#创建文件
touch

#修改用户信息
git config --global user.name "username"
git config --global user.email "email"
#查看用户信息
git config --global user.email

#创建仓库
git init

git add #(工作区 -> 暂存区) git add . 全部文件
git commit #(暂存区 -> 本地仓库)、
git commit -m "注释"

#查看日志
git log [option]
#option
#--all 显示所有分支
#--pretty=oneline 将提交信息显示为一行
#--abbrev-commit 使得输出的commitID更简短
#--graph 以图的形式显示

git status #查看状态

#版本回退 回退到commitID之前的
git reset --hard commitID
#再git reset --hard commitID 可以恢复

#查看删除的提交记录
git reflog

#添加忽略
touch .gitignore
vi .gitignore
*.md

#分支
#查看本地分支
git branch
#创建本地分支
git branch 分支名
#切换分支
git checkout 分支名
git checkout -b 分支名#创建并切换
#合并分支
git merge 分支名1 #把分支1合并到目前的branch
#删除分支
git branch -d 分支名1
git branch -D 分支名1 #强制删除
#解决冲突
当两个分支上对文件的修改可能会存在冲突，例如同时修改了同一个文件的同一行，这是就需要收到解决冲突，解决冲突步骤如下：
1.处理文件中冲突的地方
2.将解决完冲突的文件加入暂存区（add）
3.将文件提交到仓库（commit）
```
远程仓库：
```bash
#添加远程仓库
git remote add origin https://github.com/Flamevo/LearningNotes.git
#查看远程仓库
git remote
#推送到远程仓库
git push [-f][--set-upstream][远端名称[本地分支名][:远端分支名]]
#若当前分支已经和远端关联
git push
#克隆
git clone ...
#抓取
git fetch [remote name][branch name] #抓取指令就是将仓库里的更新都抓取到本地，不会进行合并
#拉取
git pull [remote name][branch name] #等同于fetch + merge
```