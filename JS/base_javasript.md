# 基础篇

##JS介绍
###基本特性
- 解释型编辑语言（脚本）
- 运行环境（各浏览器引擎）
- 区分大小写
- 注释 

```javascript
//单行注释

/*
 *这是块级注释
 *
 */
```
- 语句
  - 每个语句已; 结尾
  - 语句可嵌套
  - 多个语句可放在大括号里面
  
- 标识符
  - 第一个字符必须是字母、下划线(_)或者一个美元符号($);
  - 其他字符可以是字母、下划线、美元符号或者数字；
  - 例子: 
    - _432$fds   
    - $_fdsfds
    - ko_3
  - 一般才用驼峰大小写格式:```myCar``` ```firstSecond```
 
---

####严格模式
在严格模式下 ECMAScript 3 中一些不确定的行为将得到处理对于某些不安全的操作也会抛出错误；在整个脚本中启用严格模式在顶部添加：
```"use strict";```

指定函数体中启用严格模式：

```javascript
function doSomething{
  use strict";
  //函数体
}
```
- 关键字

```break``` ```do``` ```instanceof``` ```typeof```
```case``` ```else``` ```new``` ```var``` ```catch``` ```finally``` ```return``` ```viod``` ```continue```

- 保留字

**未补完**


- 变量
  
松散类型，可以用来保存任何类型的数据；定义变量要使用```var```后跟变量名:```var message;```

###数据类型
**5**种基本数据类型：
- Undefined
- Null
- Boolean
- Number
- String

**1**种复杂数据类型
- Object

> ECMASript数据类型具有动态性

####Undefined









































---