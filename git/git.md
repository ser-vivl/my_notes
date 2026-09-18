工作区

暂存区

本地仓库

远程仓库

  

[Learn Git Branching](https://learngitbranching.js.org/?locale=zh_CN)

### 创建仓库命令

下表列出了 git 创建仓库的命令：

|命令|说明|
|---|---|
|`git init`|初始化仓库|
|`git clone`|拷贝一份远程仓库，也就是下载一个项目。|

---

## 提交与修改

Git 的工作就是创建和保存你的项目的快照及与之后的快照进行对比。

下表列出了有关创建与提交你的项目的快照的命令：

|命令|说明|
|---|---|
|`git add`|添加文件到暂存区|
|`git status`|查看仓库当前的状态，显示有变更的文件。|
|`git diff`|比较文件的不同，即暂存区和工作区的差异。|
|`git difftool`|使用外部差异工具查看和比较文件的更改。|
|`git range-diff`|比较两个提交范围之间的差异。|
|`git commit`|提交暂存区到本地仓库。|
|`git reset`|回退版本。|
|`git rm`|将文件从暂存区和工作区中删除。|
|`git mv`|移动或重命名工作区文件。|
|`git notes`|添加注释。|
|`git checkout`|分支切换。|
|`git switch （Git 2.23 版本引入）`|更清晰地切换分支。|
|`git restore （Git 2.23 版本引入）`|恢复或撤销文件的更改。|
|`git show`|显示 Git 对象的详细信息。|

### 提交日志

| 命令                 | 说明                                  |
| ------------------ | ----------------------------------- |
| `git log`          | 查看历史提交记录                            |
| `git blame <file>` | 以列表形式查看指定文件的历史修改记录                  |
| `git shortlog`     | 生成简洁的提交日志摘要                         |
| `git describe`     | 生成一个可读的字符串，该字符串基于 Git 的标签系统来描述当前的提交 |

###  分支操作

|操作|命令|作用|
|---|---|---|
|查看分支|`git branch`|列出所有分支，当前分支前面有 `*`|
|创建分支|`git branch 名字`|新建一个分支，但还停在原分支|
|切换分支|`git checkout 名字` 或 `git switch 名字`|切到另一个分支|
|创建并切换|`git checkout -b 名字` 或 `git switch -c 名字`|新建并立刻切过去|
|合并分支|`git merge 名字`|把指定分支合并到当前分支|
|删除分支|`git branch -d 名字`|
```
git branch bugFix # 创建新分支 
git checkout bugFix #切换到新分支
# 修改内容
git commit # 提交bugFix上的修改
git checkout main # 此时还并没有融合，若是bugFix上的修改为提交此时就会融合，*号就是目前分支所在
git merge bugFix # 将bugFix的修改融入main，此时也只有main中保留了bugFix的修改
```
![[Quicker_20260918_145834.png]]
```
git checkout bugFix; git merge # 此时所以分支都包含所有的修改了
```
![[Quicker_20260918_145927.png]]




### 远程操作

|命令|说明|
|---|---|
|`git remote`|远程仓库操作|
|`git fetch`|从远程获取代码库|
|`git pull`|下载远程代码并合并|
|`git push`|上传远程代码并合并|
|`git submodule`|管理包含其他 Git 仓库的项目|

git status                 # 看工作区 vs 暂存区  
git diff                   # 工作区 vs 暂存区 的具体差异  
git diff --staged          # 暂存区 vs 本地仓库 的具体差异  
git log                    # 本地仓库的提交历史  
git log origin/main        # 远程仓库的最新提交

cd my-java-demo  
git init # 初始化git  
​  
​  
git remote add origin https://github.com/yourname/my-java-demo.git # 在远程仓库上添加  
git remote -v # 查看是否关联成功  
​  


HEAD总是指向当前分支上最近一次提交记录
checkout实际上是移动HEAD的位置

reset
revert

^ 上一个分支
~ 数字 上几个分支

rebase![[Quicker_20260918_160116.png]]
git rebase main
![[Quicker_20260918_160141.png]]
git checkout main
git rebase bugFix
![[Quicker_20260918_160356.png]]