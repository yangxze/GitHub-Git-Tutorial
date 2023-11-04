## 一、命令语言

### 1.linux常用命令

> 1. pwd: print work directory
> 2. cd: change directory
> 3. ls: list
> 4. clear
> 5. rm: remove directories  -r(recursive)递归删除
> 6. mv: move移动和重命名文件
> 7. mkdir: make directory -p(parents)递归创建（os.mkdir/os.makedirs）
> 8. chmod: change the permissions mode of a file
> 9. cat: 查看文件内容



### 2.Git常用命令

[git、github教程_哔哩哔哩](https://www.bilibili.com/video/BV1s3411g7PS/?spm_id_from=333.788&vd_source=a2b906f1078e767936dd0bbcf1275e2e)

> 1. git version/ where git
> 2. git config --global user.name  "yangxze" / git config --global user.email "77964200@qq.com"
> 3. git config --list
> 4. git status  查看当前工作区的状态 ，看看有没有未提交的代码



> 1. 添加：git add test.txt / 如果文件比较多 git add .（当前目录的全部文件）。 此时git只是暂时保存，还没有提交记录
> 2. 提交：git commit/ git commit -m "提交说明xxx"简化操作   "fix(test): change content"
> 3. 查看日志：git log 
> 4. 回退版本：git reset --hard commit id(从git  log 获得id)  hard表示重置模型（hard表示覆盖所有变更）/soft/mixed。reset操作不仅回退还清空了后面版本
> 5. 分支：git branch xx从某个主分支分出给每个人，即复制一份给自己的版本（git branch -a查看所有分支）
> 6. 切换分支：git checkout xx/master(新方式git switch -c <new-branch-name>专门用于切换分支。-c创建新分支并切换过去)
> 7. 合并：git merge xx 即把xx合并到master主分支上
> 8. 线性的提交历史：git rebase main(从当前分支整体复制到main上)
> 9. 从远程仓库获取最新的代码并将其合并到你的本地分支中：git pull(`git fetch` 和 `git merge` 命令的组合)

![image-20231102221841315](C:\Users\lanze\OneDrive\md笔记本\9插图文件\image-20231102221841315.png)

> 第一次提交
>
> 1. git branch -M main 创建一个主分支（-M用于重命名分支）
> 2. git remote add origin address（相当于给git项目设置一个网盘地址，这样git就知道需要上传到哪里）
> 3. git push -u origin main推送上传



> 工作区 => 暂存区: git add 文件名 /git add *    
>
> 暂存区 => 远程仓库: git remote add origin address -> git push -u origin main（main要推送的本地分支的名称/ -u用于设置本地分支与远程分支的关联）

![img](C:\Users\lanze\OneDrive\md笔记本\9插图文件\c3c6cace1ad741cd8789c603485bc264.jpeg)





# 二、Github contribute

步骤如下：

1. 先在github上fork你想参与的代码仓库repository，之后可以在自己的repository看到。
2. 点击repository的code的地址，通过git clone address可以克隆文件到本地。（相当于把远端的内容复制一份到本地电脑）
3. git remote -v （可以看到仓库链接），git remote add upstream other-address（添加原项目链接，添加上游代码库命令）
4. git switch -c myfun（创建并切换到myfun分支）
5. example：在原文件中加入文件member，文件下加入json文件（内容：{"name：lanze", "url: lanze-address"}）
6. 标准流程过一遍：git add .  -> git commit -m "xx" -> git push -u origin myfun
7. 回到仓库，就可以看到branch
8.  点击repository的Pull requests（简称pr），进去后点击compare & pr，最后create pr
9. 如果后续成果会显示绿色勾号(This branch has no conflicts with the base branch)，可能就是在写代码时候，原repository提交了新的commit



# 三、Others

> [列出了一些实用和救命的git操作](https://ohshitgit.com/zh)

> 1. [git commit规范](https://www.conventionalcommits.org/zh-hans/v1.0.0/)，约定式提交：
> 2. [git闯关式学习](https://learngitbranching.js.org/?locale=zh_CN)，learn git branching：

> 报错：Failed to connect to github.com port 443 /fatal: unable to access这是由于电脑里开启了代理,例如开启了翻墙软件等,就会造成这个原因
>
> 解决:取消全局代理：
> git config --global --unset http.proxy
> git config --global --unset https.proxy
>
> 或者在设置网络和internet>代理 手动编辑代理服务器，端口设置7890，然后终端输入：git config --global http.proxy http://127.0.0.1:7890

> [聊聊 Github 常见的几个按钮 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/511225962)



> **1. 什么是shell?**
>
> ​	shell是你（用户）和Linux（或者更准确的说，是你和Linux内核）之间的接口程序。你在提示符下输入的每个命令都由shell先解释然后传给Linux内核。一般来说，这个词是指操作系统中，提供访问内核所提供之服务的程序。Unix操作系统下的shell既是用户交互的程序，也是控制系统的脚本语言
>
> **2. bash是什么？**
>
> ​	shell是一种脚本语言，执行脚本语言需要解释器执行，而bash就是其中一种。bash 是 Linux 标准默认的 shell，但是同样有其他shell解释器，例如`sh`、`ksh`、`zsh`等等