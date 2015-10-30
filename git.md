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
