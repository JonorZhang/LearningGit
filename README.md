# LearningGit

## 简介
Git是目前世界上最先进的分布式版本控制系统

## 安装
Linux：`sudo apt-get install git`
macOS: `brew install git`

## 配置
```sh
git config --global user.name "YourName"
git config --global user.email "Email@xxx.com"
```

## 常用命令
- `git init`
将当前目录初始化为Git仓库，创建名为`.git`的版本管理相关的隐藏文件夹。

- `git add <file>`
把文件添加到Git仓库。

- `git commit -m <message>`
把文件提交到Git仓库。

- 要随时掌握工作区的状态，使用git status命令
- 用git diff可以查看修改内容
- HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

- 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

- 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
- 暂存区是Git非常重要的概念，弄明白了暂存区，就弄明白了Git的很多操作到底干了什么。
- 每次修改，如果不用git add到暂存区，那就不会加入到commit中
- 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

- 命令git rm用于删除一个文件

- 要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

- 要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone命令克隆。

Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。

- Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

- 当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

- 解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容，再提交。

- 用git log --graph命令可以看到分支合并图。

