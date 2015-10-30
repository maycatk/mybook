# 版本管理

**important！**

##大纲
- 版本控制系统
- 分支模型
- Git
  - Git介绍
  - 命令详解
 
###版本控制系统 VCS

版本控制系统```VCS（version control system）```是一种记录若干文件的修订记录系统，可查阅或回到某个历史版本

- "人肉"VCS  = =没有版本控制系统
- LVCS本地 
- CVCS集中式  如：SVN
- DVCS分布式  如：GIT

####人肉VCS
坑比

污染工作空间
####Local VCS 本地式
- RCS(Revision Control System)
- 协同开发不能满足需要

####CVCS集中式
- CVS
- SVN
- Perforce
由中央服务器来控制保存版本

好处：控制可控性高
弊端：单点故障，控制流畅性差

####DVCS 分布式
- Git
- Mercurial
好处：本地操作流畅性高