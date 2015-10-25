# js练习

##基础单元作业
> 1. 函数random用于生成0-999之间的随机整数。
语法如下：
```javascript
var number = random();
    number是0-999之间的整数。
```

**答案**

```javascript
function random(){
	var i = Math.floor(Math.random()*1000); //向下取整然后再取随机数[0,1)*1000
	return i;
}
var number = random();
```
---
> 2.函数multiply用于计算多个数字的乘积。
语法如下：
	```var product = multiply (number0, number1[, number2, ….])；```
使用范例如下：
```javascript
	multiply(2, 3);	 返回值： 6
	multiply(-1, 3, 4);	返回值： -12
	multiply(1, 2, 3, 4, 5);    返回值： 120
```
请写出函数multiply的实现代码。

**答案**

```javascript
function multiply(){
	var length = arguments.length,
		sum = 1,
		parameter; 
	for (var i = 0; i < length; i++) {
		parameter = arguments[i];
		sum *= parameter;
	}
	return sum;
}
var product1 = multiply(2,3); //返回值：6
var product2 = multiply(-1,3,4); //返回值：-12
var product3 = multiply(1,2,3,4,5);//返回值：120
document.write(product1 + '<br/>'); //输出6
document.write(product2 + '<br/>'); //输出-12
document.write(product3); //输出120

```
---
> 3.构造函数Person用于构造人，语法如下：
```function Person(name, age){
	// 函数体
}```
使用范例如下：
```javascript
var jerry = new Person("Jerry", 2);
	jerry.introduce();		返回值： "I am Jerry, I am 2 years old! "
var tom = new Person("Tom", 12);
	tom.introduce();		返回值： "I am Tom, I am 12 years old! "
```
请写出构造函数Person的实现代码。

**答案**


```html
function Person(name,age){
	this.name = name;
	this.age = age;
	this.introduce = function(){
		return ("I am " + this.name + ",I am "+ this.age + " years old!" + "<br/>")
	}; //构建函数体
}
var jerry = new Person("Jerry",2);   
	document.write(jerry.introduce()); //返回值： "I am Jerry, I am 2 years old! "
var tom = new Person("Tom",12);   
	document.write(tom.introduce()); //返回值： "I am Tom, I am 12 years old! "

```









