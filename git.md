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


1. git init 初始化仓库
  - git init [path]
  - git init [paht] --bare
  - rm -rf .git #添加r参数，指定删除目录 

    ```git status``` 查看git仓库信息，没初始化是看不到的；

    拓展MAC下显示隐藏文件

    ```defaults write com.apple.finder AppleShowAllFiles -bool true```

    不显示隐藏文件
    ```defaults write com.apple.finder AppleShowAllFiles -bool false ```

    **git会创建一个默认分支master**

2. git status

  - 对状态的跟踪，了解状态变化

    ```touch``` 在当前目录下创建一个新文件
3. git add 

  - 添加文件内容到暂存区(同时文件被跟踪)
  - 批量添加跟踪文件
  
    ```$ git add .``` 添加当前目录下所有的文件
    ```git rm --cached```在暂存区删除此文件

4. .gitignore 
  
  - 在添加时**忽略**匹配的文件
  - 仅作用于**未跟踪**的文件

