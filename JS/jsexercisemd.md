# js练习

##基础单元作业
函数random用于生成0-999之间的随机整数。
语法如下：
    
```javascript
var number = random();
    number是0-999之间的整数。
```
---

> 答案
```javascript
function random(){
	var i = Math.floor(Math.random()*1000); //向下取整然后再取随机数[0,1)*1000
	return i;
}
var number = random();
```



