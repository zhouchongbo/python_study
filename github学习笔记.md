# github学习笔记

## git本地文件夹的结构

![image-20220519204331926](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220519204331926.png)

![image-20220519210310016](C:\Users\28647\AppData\Roaming\Typora\typora-user-images\image-20220519210310016.png)

## 初始化git仓库

**指令：**

```shell
git init
```

**作用：生成.git目录，该目录中存放的是本地哭相关的子目录和文件，不要删除，也不要胡乱修改**

## 设置签名

**项目级别/仓库级别：仅在当前本地库范围内有效**

- ```shell
  git config user.name tom_pro
  git config user.email tom_pro@qq.com
  ```

**系统游湖级别：登录当前操作系统的用户范围**

- ```shell
  git config --global user.name tom_glb
  git config --global user.email tom_email@qq.com
  ```

**项目级别优先于系统用户级别，两种设置都有时采用项目级别**

**参看项目级别签名內容**

- ```shell
  cat .git/config
  ```

**查看系统用户范围的签名內容**

- ```shell
  cat ~/.gitconfig
  ```


## 查看状态、添加、提交

**查看工作区、暂存区状态指令：**

- ```shell
  git status
  ```

**从工作区上传新建文件/修改文件到暂存区：**

- ```shell
  git add <filenamne>
  ```

**从暂存区删除(不删除工作区文件)上传的文件：**

- ```shell
  git rm --cached <filenamne>
  ```

**从暂存区內容提交到本地库：**

- ```shell
  git commit -m "注释" <filenamne>
  ```

## 版本的前进和后退

**查看当前本地库的历史记录：**

- ```shell
  git log     ##日志全部内容
  git log --pretty=oneline  ##每个日志只显示一行
  git log --oneline
  git reflog
  ```

**后退/前进历史版本**

- ```shell
  git reflog #获取历史版本的哈希码（索引值）
  git reset --hard 哈希码
  ```

**历史版本往回退一步：**

- ```shell
  git reset--HEAD^
  ```

**历史版本往回退三步：**

- ```shell
  git reset--HEAD^^^   #依次类推^
  ```

- ```shell
  git reset --HEAD~3
  ```

## reset三个参数对比

**--soft 仅仅在本地库移动HEAD指针**

**--mixed 在本地库移动HEAD指针，重置暂存区**

**--hard 在本地库移动HEAD指针，重置暂存区，重置工作区**

## 删除本地库中的文件

**例如本地库中存在一个文件为aaa.txt，此时删除该文件的方法为：**

- ```shell
  rm aaa.txt #删除工作区中的文件
  git add aaa.txt  #将工作区的删除信息提交到暂存区
  git commit -m "delete aaa.txt" aaa.txt  #将删除信息从暂存区提交到本地仓库
  ```

**可以通过 `git reset --hard <索引号>`指令返回到之前的版本找回已经被删除的文件**

## 添加到暂存区的文件删除与找回

**可以通过 `git reset --hard <索引号>`指令返回到之前的版本找回已经被删除的文件**

## 比较文件差异

```shell
git diff <文件名>   #将工作区与暂存区中同一文件进行比较
git diff [版本索引号] <文件名>  #将工作区中的文件和本地库历史记录进行比较
```

- **不带文件名 比较所有文件**

## 分支管理

- **在版本控制过程中，使用多条线同时推进多个任务。线的概念就可以理解为分支**

- **查看当前所有分支 `git branch -v`**

- **创建新分支 `git branch <branch_name>`**

- **删除本地分支 `git branch -D branch_name`**

- **创建远程分支**

  ```shell
  git checkout -b branch_name #首先创建本地分支 分支名为branch_name
  git push --set-uupstream origin branch_name  #将创建的本地分支上传并创建远程分支
  ```

- **删除远程分支 `git push origin --delete branch_name `**

- **从当前分支转换到另一个分支 `git checkout <second_branch_name>`**

- **合并分支**

  - **切换到接受修改的分支上（一般是master）**

  - ```shell
    git checkout master
    ```

  - **利用合并分支指令合并分支**

  - ```shell
    git merge <second_branch_name>
    ```

- **冲突解决**

  - **编辑文件，删除冲突文件中的特殊符号**

  - **通过沟通把文件修改到满意程度，保存退出**

  - ```shell
    git add <冲突文件名>
    ```

  - ```shell
    git commit -m "日志信息"
    ```

  - **注意：此时的commit 千万不要加文件名**

## 本地库与远程库

- **建立本地库与远程库之间的连接**

- ```shell
  git remote add origin https://github.com/zhouchongbo/python_study.git
  ```

- **本地库內容推送到远程库**

- ```shell
  git push origin <branch_name>  #<branch_name> 指远程分支名
  ```

- **加入仓库管理之前需要先克隆远程仓库中所有的內容**

- ```shell
  git clone https://github.com/zhouchongbo/python_study.git   #https://github.com/zhouchongbo/python_study.git指远程地址
  ```

- **克隆的效果**

  - **完整地把远程库下载到本地**
  - **创建origin远程地址别名**
  - **初始化本地库**

- **邀请好友加入仓库管理**

  - **在仓库中点 `setting`**
  - **之后点 `collaborators`**
  - **输入邀请好友的github账号或邮箱**
  - **受邀请好友接受邀请**

- **其他成员修改远程库文件內容后，我们就无法将本地库推送到远程库。必须要先拉取远程库文件，才能推送本地库到远程**

  - ```shell
    git pull origin master
    ```

  - **pull指令效果等于 fetch和merge两指令的共同效果**

  - **fetch是将远程仓库中的內容抓取到本地仓库中，但是不改变工作区中文件的內容**

  - ```shell
    git fetch origin master #origing是远程地址别名 master是远程分支名
    ```

  - **merge是合并本地库与工作区中的內容**

  - ```shell
    git merge origing/master #origing是远程地址别名 master是远程分支名
    ```

  - **如果文件较为简单，如果工作区与远程库文件不太可能出现冲突可以直接用pull**

  - **当文件內容较多，比较复杂时保险起见还是用fetch+merge**

- **如果不是基于github远程库最新版所做的修改，就不能推送，必须先拉取**

- **从远程仓库拉取到本地仓库时出现冲突的解决方法**

  - **编辑文件，删除冲突文件中的特殊符号**

  - **通过沟通把文件修改到满意程度，保存退出**

  - ```shell
    git add <冲突文件名>
    ```

  - ```shell
    git commit -m "日志信息"
    ```

  - **注意：此时的commit 千万不要加文件名**
