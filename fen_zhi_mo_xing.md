# 分支模型

[示例](http://mooc.study.163.com/learn/NEU-1000054002?tid=1000102002#/learn/content?type=detail&id=1000309188)

- 分支：
    - 从目标仓库获得一份项目拷贝，每条拷贝都有和原仓库功能一样的开发线

- 分支模型(branching model)/工作流(workflow)
    - 一个围绕项目[开发/部署/测试]等工作流程的分值操作(创建合并等)规范集合


##产品级的分支模型

1. 常驻分支 *一旦生成就不会被更改*
    - development
      -从master创建
    - production(master)
      - 默认分支

2. 活动分支
    - feature
      - 从development创建
    - hotfix：如hotfix-36
      - 从master创建
    - release:如release-110
      - 从development分支创建

##特性开发
![特性图](http://i13.tietuku.com/c1d0083537fe3703s.png)

[讲解](http://mooc.study.163.com/learn/NEU-1000054002?tid=1000102002#/learn/content?type=detail&id=1000309188)