https://www.imooc.com/learn/1052



## 课程总结：

- 介绍与安装：
- 工作流： 工作区 -> 暂存区 -> 版本库
- 初始化： git init -> git add -> git commit
- 远程仓库： git remote add -> git pull -> git push -> git clone
- 分支管理： git branch -> git checkout -> git merge
- 标签管理： git tag -> git push


工作区——>暂存区（添加）
git add demo.md
git commit -m "Added demo.md"
git status

工作区<——暂存区（丢弃）
git reset HEAD demo.md
git checkout -- demo.md

>>>> edit demo.md >>>>

git add demo.md
git commit -m "Updated demo.md"
git status

git log

git reset --hard 9095da3efc45d5f....72e7
git status

git rm demo.md
git commit -m "Deleted demo.md"
git status


版本区

丢弃


创建SSH Key：
ssh-keygen -t rsa -C "youremail@example.com"

cd ~/.ssh
cat id_rsa.pub

Authenticate successfully:
ssh -T git@github.com

添加远程仓库：
git remote add origin git@github.com:tylerdemo/demo4.git

git pull origin master --allow-unrelated-histories

git push -u origin master


echo "# tyler_muke" >> README.md
git init
git add README.md
git commit -m "First commit"
git remote add origin git@github.com:tylerdemo/tyler_muke.git
git push -u origin master

git add README.md
git commit -m "Second commit"
git push

克隆仓库：
git clone git@github.com:tylerdemo/demo4.git
git status
git add index.html
git commit -m "Added index.html"
git push


查看所有标签：git tag
创建标签：git tag name
指定提交信息：git tag -a name -m "comment"
删除标签：git tag -d name
标签发布：git push origin name

确保工作目录没有git仓库：ls -a
git init
git status
echo "First branch demo" >> branch.md
git status
git add branch.md
git commit -m "Added branch.md"
git status
创建分支：git branch feature_x
查看所有分支：git branch
切换分支：git checkout feature_x
git branch
echo "New feature" >> branch.md
git add branch.md
git commit -m "New feature added"
git status
git checkout master
从feature_x分支merge到master分支：git merge feature_x
删除分支：git branch -d feature_x:





https://www.imooc.com/coursescore/751

功能分支：
- 使用develop分支作为父分支
- 每个新功能位于一个自己的分支上
- 当完成新功能时，合并回develop分支
- 新功能提交应该从不直接与master分支交互
- 分支名称：feature/[feature name]

发布分支：
- 使用develop分支作为父分支
- 这个分支只应该做bug修复、文档生成和其他面向发布的任务
- 发布完成后，发布分支应该合并到master分支并分配版本号，打好tag
- 从新建发布分支以来做的修改要合并回develop分支
- 当前发布分支名称：release/[release version No.]
- 当前发布bug修复分支名称：release-bugfix-[Version No.]/[bug name | bug No.]

维护分支：
- 唯一可以直接从master分支fork出来的分支
- 修复完成，修改应该马上合并回master分支和develop分支
- master分支应该用新的版本号打好tag
- 分支名称：hotfix/[bug name | bug No.]