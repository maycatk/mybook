# Git

简介网上就有


##Git命令

###基本操作
- git config *在使用git之前配置*
配置git
  - 用户配置   
    - ```git config --global user.name "Han jam"//用户名```
    - ```git config --global user.email test@example.com // 用户邮箱       ```   
  - 配置级别
    - --local [默认，高优先级]：只影响本仓库   ```.git/config```
    - --global [中优先级] ： 影响到所有当前用户的git仓库  ```~/.gitconfig```
    - --system [低优先级] ： 影响到全系统的git仓库  ```/etc/gitconfig```


- git init 初始化仓库
  - git init [path]
  - git init [paht] --bare
  - rm -rf .git #添加r参数，指定删除目录 

    ```git status``` 查看git仓库信息，没初始化是看不到的；

    拓展MAC下显示隐藏文件

    ```defaults write com.apple.finder AppleShowAllFiles -bool true```

    不显示隐藏文件
    ```defaults write com.apple.finder AppleShowAllFiles -bool false ```

    **git会创建一个默认分支master**

- git status

  - 对状态的跟踪，了解状态变化

    ```touch``` 在当前目录下创建一个新文件
    
    
- git add 

  - 添加文件内容到暂存区(同时文件被跟踪)
  - 批量添加跟踪文件
       
```$ git add .``` 添加当前目录下所有的文件
    
- \.gitignore 

  
  - 在添加时**忽略**匹配的文件
  - 仅作用于**未跟踪**的文件
  - 只是忽略文件


- 从暂存区删除git-rm
 
  - ```git rm --cached```仅在暂存区删除此文件
  - ```git rm :```从暂存区和工作目录都删除
  - ```git rm $(git ls-files-deleted)```删除所有被跟踪，但是在工作目录被删除的文件


- 工作目录与暂存区

- git commit
  - 根据暂存区内容创建一个提交记录
  - 直接提交
 
- git log
  - 查看提交记录
  - ```git log --oneline```   ```git log```

> git log 可以获得提交作者、提交信息、表示提交的hash值信息
  
  
- git中的alias命令
  - 长长命令行精简~~~~

```git config alias.shortname <fullcommand>```


```git
git config --glocal alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bordblue)<%an>%Creset' --addrev-commit"
```

---

- git diff
显示不同版本的差异,工作目录渝暂存区的差异

- git diff -cached[<reference>]
  - 暂存区与某次提交差异，默认为HEAD

- git diff <reference>
  - 工作目录与某次提交的差异

- 撤销本地修改
  - ```git checkout -- <file>```


- 撤销暂存区内容
```git reset HEAD <file>```

将文件内容从上次提交复制到暂存区 = 暂存区没有进行修改

- 撤销全部改动

 ```git checkout HEAD -- <file>```
 暂存区和工作目录一致
 
##总结

![git总结](http://i11.tietuku.com/4cd3ab585a7bb6f7s.png)




---

> branch、checkout、reset、reset-vs-checkout、merge、rebase、rebase-vs-merge、tag


> ```git checkout --<filename>```和```git checkout <filename>```  中的"--"的作用
> 为了避免```git checkout <branch>```有重名冲突 "--"后跟```<filename>```默认是文件名不是分支名

[点击查看问题参照](http://stackoverflow.com/questions/6561142/difference-between-git-checkout-filename-and-git-checkout-filename)


##分支操作
- git branch  分支的增删查改
  - git branch <branchName> 创建分支
  - git branch -d <branchName> 删除指定分支 
  - git branch -v 显示所有分支信息

- 使用
  - git checkout用来移动HEAD
  - git checkout <branchName> 直接指向目标分支
  - git checkout -b <branchName> 直接创建分支并指向
  - git checkout <reference>
 

```git checkout -```回去上一个分支
  - git checkout -b issue-26  创建分支issue-26并移动
  - git branch -v 查看分支
  - detached head! 分离状态下得HEAD 

























