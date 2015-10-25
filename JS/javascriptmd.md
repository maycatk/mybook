# Javascript程序设计

**10月26日   10:00截止提交所有的作业和考试**

---------------------------
###JS介绍
####基本特性
- 解释型编辑语言（脚本）
- 运行环境（各浏览器引擎）
##基本语法
###语句
- 每个语句已; 结尾
- 语句可嵌套
- 多个语句可放在大括号里面
- 注释 
	- 单行注释 //
	- 块级注释 /* 开头     */
		- 不可嵌套

--------
##基本类型
###Number
- 整数
	- 15
	- var num = 10;
	- 0377 八进制
	- 0xff   十六进制
- 浮点数
	- 1.2
	- var num - 3.1416
	- 1.4E2  
- 特殊值
	- NaN(Not a Number)
	- Infinity 无穷大
###String
- 字符串 用""   '' 引用起来的
###Boolean
- true
- false 
- 必须小写
###Object
- Object是一组无序的名值对的集合
```javascript
var cat = {
	name:'kitty',
	age:2, //直接量直接定义
	mew:function(){ //方法
		console.log('喵喵喵');
}
}
```
		var dog = new Object();//用new来定义
###Null
- 类型说明
	- 值：null
- 出现场景
	- 表示对象不存在
	- var car = null;
###Undefined
- 值
	- undefined
- 出现场景
	- 已声明未赋值的变量
	- 获取对象不存在的属性

###类型识别
- typeof
![Alt text](./1443799745017.png)

###原始类型和引用类型
- 原始类型
	- Number
	- String
	- Boolean
	- Object
	- Null
	- Undefined
	
		var num1 = 123;
		
- 引用类型
	- Object

		var obj1 = {a:1};

- 对比
原始类型值不变
![Alt text](./1443802663556.png)

-------
##操作符和表达式
####一元操作符
![Alt text](./1443803046844.png)				

前++ 是先加赋值
![Alt text](./1443803198691.png)

后++先赋值在操作
![Alt text](./1443803229650.png)

####算术操作符
![Alt text](./1443803249321.png)

####关系操作符 
![Alt text](./1443803290260.png)
返回布尔类型

####相等操作符
![Alt text](./1443803338051.png)
----
转换类型
![Alt text](./1443803418929.png)

----
- === 全等

####逻辑操作符
![Alt text](./1443803472521.png)
- ！
例子
![Alt text](./1443803550327.png)

----
- && 逻辑与
or 相当于and 并且 相乘
	- ![Alt text](./1443803656160.png)
	- 如果第一个数为true 结果为第二个数 如果第一个为false结果为第一个数。
	- ![Alt text](./1443803746836.png)
	- 短路操作
- ||逻辑或
	- ![Alt text](./1443803798911.png)
	- 如果第一个操作数为true结果为第一个数 反之;
	- ![Alt text](./1443803857477.png)
	-  短路操作

- 例题
		var a = 0;
		var b = 0||++a;
	a,b值分别为1，1;

####赋值操作符
- =
		var num = 5; //5
		num = num + 5; //10
		num +=5;//
- +=
- -=
- *=
- /=
- %=

####条件操作符
- ? :
- 布尔表达式？表达式一:表达式二;
- true为表达式一
- 例子
- ![Alt text](./1443804209119.png)

####逗号操作符
- ，
![Alt text](./1443804269728.png)

####对象操作符
- new
	- 通过这个可获取一个实例 
- delete
	- 可删除一个对象属性
- .
	- 获取一个对象的属性
- []
	- 获取对象属性值 
- instanceof
	- 可判断某个变量是否为某个对象的实例
- in
	- 可判断某个属性是否在对象中
####位操作符
![Alt text](./1443804549195.png)
转换为二进制在操作

####操作符优先级
> 下表列出了 JavaScript 运算符，并按优先级顺序从高到低排列。 具有相同优先级的运算符按从左至右的顺序计算。
| 运算符      |  说明 | 
| :-------- | :--------| 
| .[ ] ( )    |   字段访问、数组索引、函数调用和表达式分组 | 
| ++ -- - ~ ! delete new typeof void    |   一元运算符、返回数据类型、对象创建、未定义的值 | 
| * / %  |   相乘、相除、求余数 | 
| + - +    |   相加、相减、字符串串联 | 
| << >> >>> | 移位 | 
| < <= > >= instanceof |   小于、小于或等于、大于、大于或等于、是否为特定类的实例 | 
| == != === !== |   相等、不相等、全等，不全等 | 
| &  |   按位“与” | 
| ^ |   按位“异或” | 
| &brvbar;  |   按位“或” | 
| && |   逻辑“与” | 
|   &brvbar; &brvbar;  |   逻辑“或” | 
| ?: |   条件运算  | 
| = OP= |   赋值、赋值运算（如 += 和 &=）  | 
| , |   多个计算  | 

####表达式
> (5+3)*(6-3)|| !flag

-------
> [运算符优先级网页](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
> [javascript中的相等性判断](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Equality_comparisons_and_sameness)

##语句
###条件语句
####if(条件){语句1}else{语句2}
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>js</title>
	<script>
	document.write("<h3>hello.world!</h3>")
	var isMale = false;
	if (isMale) {
		document.write('男');
	}else{
		document.write('女');
	}
	</script>
</head>
<body>
	
</body>
</html>
```
> 不管语句长短尽量都用大括号便于后期维护

####if(条件){语句1}else if(条件2){语句2}else{语句3}
> 多种条件下的判断语句
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>js</title>
	<script>
	var score = 65;
	if (score > 70 ) {
		document.write('A');
	}else if (score >= 60) {
		document.write('B');
	}else{
		document.write('C');
	} //B
	</script> 
</head>
<body>
</body>
</html>

```

####switch
	switch(表达式){
		case 值1:语句
			break；
		case 值2:语句
			break；
		case 值3:语句
			break；
		default:语句
	}

-----
###循环语句
####while
> while(表达式){语句}
> 表达式为真执行语句
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>while</title>
</head>
<script>
var i = 1;
while(i <= 12){
	document.write(i);
	i++;
}
</script>
<body>
	
</body>
</html>
```

####do - while
> do{语句}while(表达式)
>不管表达式是否为真先执行do 语句，然后根据表达式是否为真而判断是否继续执行do 语句

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>dowhile</title>
<script>
var i = 0;
do{
	document.write(i);
	i++;
}
while(i <= 10 ) //012345678910 i<=10时不继续执行do语句
</script>
</head>
<body>
</body>
</html>
```
####for 
> for(初始化；循环条件；更新表达式){语句}
> 一遍又一遍地运行相同的代码，并且每次的值都不同
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>for</title>
<script>
/*var i = 1;
while(i<=10){
	document.write(i);
	i++;
}	//12345678910

*/

for (var i = 1; i <= 10; i++) {
	document.write(i);//12345678910
};
</script>
</head>
<body>
	
</body>
</html>
```
####break,continue 控制循环

- break
	- ![Alt text](./1443811701225.png) //1234
	- 跳出整个循环体
- continue
	- ![Alt text](./1443811748081.png) //1234678910
	- 跳出这次的循环体，再接着下一次循环 
####for in 
> for(属性名 in 对象 ){语句}
> 可以遍历对象中的属性名
```javascript
var cat ={
	name : 'kitty',
	age : 2,
	mew:function(){
		console.log('喵喵喵');
	}
}
for(var p in cat){
	document.write(p);
}//nameagemew
```
####with
> with(表达式){语句}
> 对同一个对象进行多次操作
```javascript
var kitty = {
		age:3,
		friend : {
			name : 'snoopy',
			age :2,
		}
	}
	/*document.write(kitty.friend.name +'\'s age is' + kitty.friend.age);//snoopy's age is2*/
	// 转换成with语句
	with(kitty.friend){
		document.write(name+'\'s age is' + age);
	}
```

####异常捕获语句
	try{
		语句
	}catch（exception）{
		语句
	}finally{
		语句
	}

测试语句

```javascript
try{
	document.write(notDefined); //验证正确
}catch(error){
	alert(error); //出错就会跳到这里
}finally{
	alert('finally'); //最后执行
```
###数值

-------
####运算方法

#####Math.abs(x) 绝对值
	Math.abs(- 4); //4
	Math.abs(4);//4 
> 取绝对值
 
 
#####Math.round(x) 四舍五入
	Math.round(1.6) ;//2
	Math.round(1.1) ; //1
>四舍五入取值
>可以把一个浮点型数值变为一个整型数值

#####Math.ceil(x)  向上取整
	 Math.ceil(1.1);//2
	 Math.ceil(1.9);//2
 
#####Math.floor(x)  向下取整
	 Math.floor(1.1);//1
	 Math.floor(1.9);//1
	 
######对比图例
![Alt text](./1444152907990.png)

#####Math.max([value1[,value2[,...]]])  获取最大值
	Math.max(1,2)//2
	Math.max(-1,-2,-3)//-1

#####Math.min([value1[,value2[,...]]])  获取最小值
	Math.min(1,2)//1
	Math.min(-1,-2,-3)//-3

#####Math.random() 获取一个大于等于0小于1的值
	Math.random()//0.23213
	Math.random()//0.64345
	Math.random()//0.32543

#####Math的其他方法
![Alt text](./1444153167811.png)

#####parseInt(string,radix)    --radix 设定进制 ---字符串转换成整数
>一般javascript获取的数值是一个字符串 得使用parseInt来转换成整型

		parseInt('1.1') //1
		parseInt('1.9') //1
		parseInt('1b2.4') //1
		parseInt('www') //NaN (not a number)

#####parseFloat(string) 字符串转换成浮点型
> 有小数点保留需求转换

	parseFloat('100.1') //100.1
	parseFloat('12.4b5') //12.4
	parseFloat('www') //NaN

#####Number(value) 转换成数字
	Number('100.1') //100.1
	Number('12.4b5') //NaN
	Number('www') //NaN
>对于付款数字判断定义Number更适合
######转换数值类型对比
![Alt text](./1444153947427.png)

#####num.toFixed(digits) 保留小数点 ----digits为保留几位小数点
	(100.123).toFixed(2)  //输出字符串“100.12”
	(100.123).toFixed(0)  //输出字符串“100”

######代码示例 
**获取一个大于等于0且小于等于9的随机整数**

    var n = Math.floor(Math.random()*10);//先取[0,10)一个随机数,然后向下取整；
	console.log(n); //控制台输出

###字符串
> 表示格式 "哈哈哈哈"   "2324324"  "" "http://www.huhu.com"   
> 单引号 === 双引号

####str.length 判断字符串长度

    "micromajor".length //10
 
 **实际操作中比如判断输入** 
 ![Alt text](./1444165223532.png)
 
	 var userName = input.value ; //获得"micrmajor"
	 if(userName.length < 6){
	 alert("昵称要求大于等于6个字符")};

####str.charAt(index) 返回指定位置的字符


    "micromajor".charAt(0) //"m"
 
>字符索引值:
>
>![Alt text](./1444165843780.png)


**实例 判断字符规则**
![Alt text](./1444165516562.png)

    var userName = input.value; //"-micromajor"
    if(userName.charAt(0)=="-"){
		alert("昵称不能以"-"开头");
	}

####str.indexOf(searchValue[,fromIndex]) 定位字符串中某一个指定字符首次出现的位置

    "micro-marjor".indexOf("-") //5 -的索引位置是5
    "micro-marjor-web".indexOf("-") //5 只返回第一个位置
    "micro-marjor".indexOf("major") //6 字符串得第一个位置
    "micromarjor".indexOf("-") //-1 找不到的值返回-1


**实例演示 判断字符串中得文字有没有某元素**
>![Alt text](./1444166245743.png)

    var userName = input.value;//"micromajor"
    if(userName.indexOf("-") == -1){
	    alert("昵称必须包含"-"");
    }


####str.search(regexp)  用正则方法来查找

    "micromajor".search(/[0-9]/) //-1 没有数字返回-1   
	 "micromajor11".search(/[0-9]/) //有数字 返回索引值 10

![Alt text](./1444166855679.png)

    var userName = "micromajor163"; //"micromajor163"
	if (userName.search(/[0-9]/) != -1 ) {  //判断0到9的数字集合， !=-1表示有数字
	alert("昵称不能含有数字");
	}; 

####str.math(regexp) 查找匹配
	"micromajor163".match(/[0-9]/) //返回一个数组["1"] 返回的不是索引；
	"micromajor163".match(/[0-9]/g) //匹配到所有的数字 添加一个全局参数g 返回["1", "6", "3"]
	"micromajor11".search(/[A-Z]/) //没有匹配结果 返回 null

####str.replace(regexp|substr,newSubstr|function)  查找替换
	"micromajor163".replace("163","###")	//"micromajor###" 字符替换
	"micromajor163".replace(/[0-9]/,"#") //"micromajor#63" 只匹配到第一个索引值
	"micromajor163".replace(/[0-9]/g,"#") //"micromajor###"全局匹配 
	"micromajor163".replace(/[0-9]/g,"") //"micromajor"
####str.substring(indexA[,indexB]) 查找索引值截取字符串 传入负数转换为0 或者无效
	"micromajor".substring(5,7) //"ma"  A值包含B值是不包含的 截取到索引[5,7)
	"micromajor".substring(5) //"major" 从索引5开始后面的字符串都截取出来
	"helloworld".substring(2,-2) //"he"  取值范围里有负数时只返回第一个值为位数的字符串
	"helloworld".substring(-2) //"helloworld" 是单个负数值参数直接转换为0 取全部字符串
####str.slice(beginSlice[,endSlice]) 提取字符串 可以传入负数
	"micromajor".slice(5,7) //"ma"  
	"micromajor".slice(5) //"major"
	"micromajor".slice(1，-1) //"icrmajo" 索引1字符串到字符串倒数-1的位置
	"micromajor".slice(-3) //"jor" 从倒数第三开始到最后
####str.substr(start[,length]) 从某一个位置开始取某个长度的字符串
	"micromajor".substr(5,2) //"ma"
	"micromajor".substr(5) //"major" 
	
####str.split([separator][,limit])  把字符串分割为字符串数组。

    "micro major".split(" ") //["micro","major"] 以空格为分隔符输出字符串数组
	"micro major".split(" ",1) //["micro"] 限定输出个数
	"micro2major".split(/[0-9]/) //["micro","major"] 用正则已数字做分隔符
**运用场景**
![Alt text](./1444213644578.png)

####str.toLowerCase() 把字符串全变成小写

    "MicroMajor".toLowerCase() //"micromajor" 都转换成小写
    
####str.toUpperCase() 把字符串全变成大写

	"MicroMajor".toLowerCase() //"MICROMAJOR" 都转换成大写

####连接

    "0571" + "-" + "88888888" //"0571-88888888"
    ---------------------------------------------
    var area = areaInput.value;
    var tel = telInput.value;
    var number = area + "-" + tel; //"0571-888888"

![Alt text](./1444214559748.png) 两个数据javascript提取的时候是两个字符串要连接字符串才能实现需求 

####String()  转换成字符串

    String(163) //"163"
    String(null) //"null" 转换成字符串

####转义 
> 比如字符串中要求有""存在
>      "hahah"ahha" //会报错
> 解决:"hahah\"aha" //hahah"aha

###对象
> 拥有一些属性一些方法的个体
####创建对象

    new Object()
    -----------------
    var car = new Object(); //方法一
    var car ={}; //方法二 直接量 常用方法
 
####属性和方法

    var car ={
		color : "red", //两个属性用，分开
		run : function(){alert("run")} //可以赋方法
	};
	/*访问属性方法*/
	car.color; //"red" 获取属性值
	car.run(); //alert("run")  获取属性方法
	car["color"]; //"red" 
	car["run"](); //alert("run")

#####增加属性和方法

    var car = {
		color : "red",
		run : function(){alert("run")}
	};
	/*添加属性方法*/
	car.type = "suv"; //直接赋值增加属性
	car.stop = function(){alert("stop")}; //增加添加方法
	/*修改属性方法*/
	car.color = "white";//重新赋值
	car.run = function(){alert("run2")};//重新赋方法
	/*删除属性方法*/
	delete car.color; //删除属性
	car.color //undefined
	delete car.run(); //删除方法
#####obj.constructor 对象构造

    var car = {
	    color :"red",
	    run : function(){alert("run")}
    };
    car.constructor; //object
    --------------------
    var num = new Number(123);
    num.constructor; //Number

#####obj.toString() 对象转换成字符串

    var num = new Number(123);
    num.toString() //"123"
#####obj.valueOf() 获取对象原始值

    var num = new Number(123);
    num.valueOf()  //123

#####obj.hasOwnProperty()判断对象是否有某个特定的属性。必须用字符串指定该属性 返回一个布尔值

    var car = {
	    color :"red",
	    run : function(){alert("run")}
    };
    car.hasOwnProperty("color")  //true
    car.hasOwnProperty("logo") //false
    ================================
    还可判断对象里的属性是否是通过继承而来
   

###数组
####创建数组

    var array = new Array();//1.new一个数组
    var array = []; //2.直接量
    var array = [1,6,3];
    var array = [
	163,
	"hahah",
	{color:"red"},
	[],
	ture
	] //数组里面每个类型都可以不一样

![Alt text](./1444244842817.png)
#####arr.length 数组长度数组里面的元素个数
![Alt text](./1444244903358.png)

    students.length; //3
    students = [];
    students.length; //0

#####获取数组元素

    students[0]; //{id:1,score:80}索引位置直接获取
    students[0].score;//80
#####修改数组元素

    stude**strong text**nts[1].score = 60;//直接修改
#####arr.indexOf(searchElement[,fromIndex = 0]) 找出数组中得元素并输出索引位置 默认从0开始

    var tel = [110,120,114];
    tel.indexOf(123); //1
    tel.indexOf(119); //-1
#####arr.forEach(callback[,thisArg]) 数组循环遍历
????
> forEach()是javascript扩展到ECMA-262标准某些时候可能不存在标准其他实现，需要添加

    if (!Array.prototype.forEach){
		Array.prototype.forEach = function(fun /*, thisp*/){
	var len = this.length;
	if (typeof fun != "function")
		throw new TypeError();

	var thisp = arguments[1];
	for (var i = 0; i < len; i++){
		if (i in this)
			fun.call(thisp, this[i], i, this);
			}
		};
	}
	
#####arr.reverse() 倒序数组索引

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	]；
	students.reverse();
	students[0].score;   //70 倒序 
#####arr.sort([compareFunction]) 排序方法 

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	]；
	var byScore = function(a,b){
		return b.score-a.score; //倒序
		return a.score-b.score; //升序				
	};
	students.sort(byScore); //结果为已成绩进行倒序排列
	======================
	调用方法时没有传入参数
	var studentNames = ["wq","xl","gp"];
	studentNames.sort();
	studentNames;//["gp","wq","xl"] 按照Unicode编码顺序排列
#####arr.push(element1,...,elementN) 在已有数组向后插入数据

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	]；
	students.push({id:4,score:90});
	//
	[
	{id : 1,score:80},	
	{id : 2,score:50},	
	{id : 3,score:70},
	{id : 4,score:90},
	]
#####arr.unshifet(element1,...,elementN) 向前添加插入
与push相反
#####arr.shift() 获取数组第一个元素并在原数组删掉这个元素

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	]；
	students.shift(); //{id :  1,score:80} 原本数组没有id:1 元素

#####arr.pop() 获取数组最后一个元素 并删除

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	]；
	students.pop(); //在后面获取{id :  3,score:80} 

#####arr.splice(index,howMany[,ele1[,...[,eleN]]]) 在数组中部插入项
> splice()  可**删除**，**插入**，**替换**

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	]；
	students.splice(1,1,{id:4,score:90});
	//var students = [{id : 1,score:80},{id : 4,score:90},{id : 3,score:70},]；
	//在索引1插入一个{id:4,score:90} 删除索引1 位置元素 删除替换效果
	students.splice(1,1) //删除效果
	students.splice（1，0，{id:4,score:90}）;//插入

#####原数组被修改的方法：reverse,sort,push,unshift,shift,pop,splice

#####arr.slice(begin[,end]) 返回数组中的元素创建新数组 负数参数从后开始数 参数的第二个值是不包含的

    var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	];
	var newStudents = students.slice(0,2);//[{id : 1,score:80},{id : 2,score:50},]
	var newStudents = students.slice(0);//全部复制数组
	var newStudents = students.slice(0,-1);//[{id : 1,score:80},{id : 2,score:50},]
	
#####arr.concat(value1,...,valueN) 连接数组
![Alt text](./1444485253126.png)

    var newStudents = students1.concat(students2,students3);//三个班的成绩单都连起来显示
    
   ![Alt text](./1444485304393.png)
#####arr.join([separator]) 数组设置元素分割连接成一段字符 默认用，

    var emails = ["wq@166.com","ko@432.com","d3421@fds.com"];
    emails.join(";");
    //"wq@166.com;ko@432.com;d3421@fds.com"
#####用遍历forEach()不改变老数组情况下创建新数组
    var score = [60,30,90,70];
	 var newScores = [];
	 var addScore = function(item,index,array){
 	newScores.push(item+5);
	 };
	 score.forEach(addScore);
	 newScores;//[65, 35, 95, 75] 每项分值加5

#####arr.map(callback[,thisArg]) 数组遍历自动添加

    var addScore = function(item,index,array){
 	return item+5;
	 }
	score.map(addScore); //[65, 35, 95, 75]
> score.map()方法回调的数组

#####arr.reduce(callback,[initialValue])  方法接收一个函数作为累加器（accumulator），数组中的每个值（从左到右）开始缩减，最终为一个值。

```javascript
	var students = [
		{id : 1,score:80},	
		{id : 2,score:50},	
		{id : 3,score:70},	
	];
	var sum = function(previousValue,item,index,array){//previousValue方法先前的结果，item当前的元素，index当前的索引位置
	return previousValue+item.score;
	};
	students.reduce(sum,0); //200
```
#####slice,concat,join,map,reduce对原来的数组没有修改
###函数
####函数语法

    function add(number0,number1){
		var sum = number0+ number1;
		return sum;
	}
	var x = add(2,3);
function 函数名([形参列表]){
	执行代码
}

函数名([实参列表])  //函数调用

####函数的定义
1. 函数声明
![Alt text](./1444500449397.png)
2. 函数表达式
![Alt text](./1444500472570.png)

> 函数表达式的语法格式是将匿名函数赋值给一个变量。
####函数调用
实参列表赋值给了形参列表进行运算，返回函数中得值
####函数参数
- 实参的数量少于形参
![Alt text](./1444500893468.png)
> 返回NaN

- 实参数量多余形参
![Alt text](./1444501823107.png)

####实参不定的需求
![Alt text](./1444502180750.png)

```javascript
function add(){
	var length = arguments.length,
		sum = 0,
		parameter;
	for (var i = 0; i < length; i++) {
		parameter = arguments[i];
		sum = sum + parameter;
	}
	return sum;
}
x = add(2,1);
y = add(2,1,4);
document.write(x +<br/>);
document.write(y);
```
> 函数调用时，实参数量不一定要等于形参数量。

- 参数为原始类型   

> 值传递
```javascript
值传递
function increment(number){
	number = number +1;
	return number;
}
var a = 1;
var x = increment(a); //2  参数是原始类型
a ; //1 不变 number变 
```
- 参数为对象类型： 引用传递
```javascript
function increment(person){
	person.age = person.age +1;
	return person;
}
var jerry = {name:'jerry',age:1};
var x = increment(jerry); //{name:'jerry',age:2}
jerry; // name:'jerry,age:2' 原对象属性改变
```
####作用域
 - 变量起作用的范围
 
```javascript
var jojo = {
	name:"jojo",
	gender:1
};
function class1 () {
	var jojo = {
		name:"jojo",
		gender:0
	};
	jojo.name = "jiji";
	jojo.gender = 1;
}
class1();
jojo;//{name:jojo,gender:1}
```
```javascript
var jojo = {
	name:"jojo",
	gender:1
};
function class1 () {
	jojo.name = "jiji";
	jojo.gender = 1;
}
class1();
jojo;//{name:jiji,gender:1}
```

> 函数的作用域限制了函数中变量的作用范围。
####函数作为对象属性

    var point = {
	x:1,
	y:1,
	move: function(stepX, stepY){
		point.x +=stepX;
		point.y +=stepY;
	}
	};
	point.move(2,1);
	--------------------
	等于
	var point = {
	x:1,
	y:1,
	move: function(stepX, stepY){
		this.x +=stepX;
		this.y +=stepY; //相等
	}
	};
	point.move(2,1);
####构造函数

```javascript
function Point(x,y){
	this.x = x;
	this.y = y;
	this.move = function(stepX,stepY){
		this.x += stepX;
		this.y += stepY;
	}
}
var point = new Point(1,1);//构造函数的调用
var point2 = new Point(2,2);
var point3 = new Point(3,3);//....
```

####原型
```javascript
function Point(x,y){
	this.x= x;
	this.y = y;
}
Point.prototype.move = function(stepX,stepY){ //原型 公共的属性
	this.x +=stepX;
	this.y +=stepY;
};
var point = new Point(1,1);//x:1,y:1
point.move(2,1);//{x:3,y:2}
```

###Date

![Alt text](./1444577424152.png)
表示时间
> 月份是从0 开始
####创建日期
- new Date()    //创建当前日期
- new Date(value)   //传一个日期
- new Date(year,month[,day[,hour[,minutes[,seconds[,milliseeconds]]]]]) //通常传入日期的用法

![Alt text](./1444577607919.png)
####date.getXXX()  获取信息

    var date = new Date(2015,7,20,14,57,18)
    date.getFullYear(); //2015 获取年
	date.getMonth();
	date.getDate();
	date.getHours();
	date.getMinutes();
	date.getSeconds();

####格式化
![Alt text](./1444577946092.png)
实际效果
------

格式化
------

```javascript
function padding(number){ //补零
	return number < 10 ? '0' + number :'' + number;
}
function format(date){
	return date.getFullYear() + '-'
	+ padding(date.getMonth() +1) + '-'
	+ padding(date.getDate()) + ' '
	+ padding(date.getHours()) +':'
	+ padding(date.getMinutes())+ ':'
	+ padding(date.getSeconds());
}
var date = new Date();
alert(date); //没有格式化
alert(format(date)); //已格式化
```

####date.setXXX() 设置
![Alt text](./1444578655947.png)
设置日期

    date.setDate(35);//日期超过正常数 会向后自动转成下个月的日期 同理时钟也是

####求天数

    new Date(2001,2,0) //三月第零天 == 二月最后一天 得到的日期就是二月的天数
   
```javascript
function getDays(year,month){
	var date = new Date(year,month,0);
	return date.getDate();
};
	alert('2001年2月有' + getDays(2001,2) + '天');
	alert('2001年3月有' + getDays(2001,3) + '天');
```
####Date>Number
日期转换成Number 前端传入后段时
- date.getTime(); 
![Alt text](./1444579310758.png)
####Number>Date
![Alt text](./1444579404491.png)

###RegExp 正则表达式
####正则表达式
- 描述字符串规则的表达式
	-  /pattern/attrs    ----/规则/属性 直接量
	-  new RegExp(pattern,attrs)   ----对象构造（规则，属性）

####regexObj.test(str)
- 测试正则表达式与制定字符串是否匹配 返回true ,false

    /135888884444/.test('1358839393');//false
 
> 实例
```javascript
	<input type="text" onblur="check(this)" onfocus="reset(this)">
	<script>
		function check(mobileInput){
			var value = mobileInput.value;
			if (!/13566668888/.test(value)) {
				mobileInput.style.borderColor = 'red';
			};

		}
		function reset(mobileInput){
			mobileInput.style.borderColor = '';
		}

	</script>
```
> test只会判断属性中是否跟test中有相匹配的字符串 多出的字符也会返回true
####锚点
- 匹配一个位置
	-  ^:起始位置       `/^http:/ -----url起始位置匹配`
	-  $:结尾位置        `/\.jpg$/   ----.jpg结尾的位置`
	-  \b:单词边界        `/\bis\b/     ------` 

####字符类
- 匹配一类字符中的一个
	- [abc]:a或b或c
	- [0-9]: 一个数字   [ ^ 0-9 ]:非数字的一个字符
	- [a-z] :一个字母 
	- . :任一字符（换行除外）
> 实例 判断电话填入框正确
```javascript
<input type="text" onblur="check(this)" onfocus="reset(this)">
	<script>
		function check(mobileInput){
			var value = mobileInput.value;
			if (!/^1[0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]$/.test(value)) {
				mobileInput.style.borderColor = 'red';
			};

		}
		function reset(mobileInput){
			mobileInput.style.borderColor = '';
		}
```

####元字符
- 具有特殊意义的字符
	- ^、$、\b--数字
	- \d:[0-9]     \D:[ ^ \ d ]   
	- \s: 空白符     \S :[ ^ \s]   
	- \w: [A-Za-z0-9_] 单词字符  \w:[ ^\w]
 

```javascript
/^1[0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]$/
-------------------------------------------------------
/^1\d\d\d\d\d\d\d\d$/
--------------------
```
####量词
- 出现的次数
	- {m,n}: m到n次
	-   *  ： {0,}
	-  ? : {0,1}
	-  + : {1,}
> 实例改写
```javascript
/^1\d\d\d\d\d\d\d\d$/
--------------------
/^1\d{10}$/

```
####转义符
- 需要匹配的字符是元字符

    - `/^http:\/\//`   加反斜杠进行转义
    - `/@163\.com$/`  .加反斜杠反义

####多选分支
- 或 `/thi(c|n)k/` thick 或 think    === `/thi[cn]k/`
- `/\.(jpg|png|jpeg|gif)$/` 检测图片文件
####获取
- 保存匹配到的字符串，日后再用
- () :捕获   ![Alt text](./1445350469596.png)
- (?:) :不捕获   ![Alt text](./1445350559646.png)
- 使用：
	-    $1,$2,......
	-  api参数或返回值

####str.match(regexp)
- 获取匹配的字符串
![Alt text](./1445351808985.png)
####str.replace(regexp/substr,replacemrnt)
- 替换一个子串
```javascript
var str = 'The price of tomato is 5.';
str.replace(/(\d+)/,'$1.00');
```
格式化只能格式化第一个元素
----

全部替换要用全局属性     /g
####regexpObj.exec(str)
- 更强大的检索
	- 更详尽的结果：index
	- 过程的状态：lastIndex
##JSON
- JSON对象包含了两个主要方法，一个方法用来将JavaScript值转换为JavaScript Object Notation (JSON)格式的字符串，另外一个方法用来将JSON字符串转换为JavaScript值。
###JSON.parse()
![Alt text](./1445356392943.png)
- 将一个 JSON 字符串解析成为一个 JavaScript 值
语法
----
    JSON.parse(text[, reviver])

例子
----

    JSON.parse('{}');              // {}
	JSON.parse('true');            // true
	JSON.parse('"foo"');           // "foo"
	JSON.parse('[1, 5, "false"]'); // [1, 5, "false"]
	JSON.parse('null');            // null
>JSON.parse() 不允许逗号结尾
IE兼容
```javascript
if(!window.JSON){
	window.JSON={
		parse:function(sJSON){
			return eval('('+sJSON+')');	
		}
	};
}

```

###JSON.stringify()
- JS > JSON
- 方法可以将任意的 JavaScript 值序列化成 JSON 字符串。
	
		JSON.stringify(value[, replacer [, space]])
兼容
```javascript
if(!window.JSON){
	window.JSON = {
		parse:function(sJSON){
			return eval('(' + sJSON + ')');
		}
		stringify:function(){
			//....
		}
	};
}
```

##进阶类型
- Undefined
- Null
- Boolean
- String
- Number
原始（值类型）

--------

- Object
对象（引用）类型

###对象类型
![Alt text](./1445361601749.png)

####浏览器扩展对象
正在弃用
####宿主对象
提供DOM、BOM操作对象  重要‘
####原生对象
#####构造函数

#####对象

> JS中的函数是对象函数
###原始类型和对象类型的区别
![Alt text](./1445361980737.png)
访问对象内存必须得f.a访问
- 原始类型
![Alt text](./1445362055992.png)
- 对象类型
![Alt text](./1445362123078.png)
对象类型复制只是复制一个地址值
> 如何复制一个对象？
###隐式类型转换
实例：
![Alt text](./1445362255005.png)
- 所有的数字运算符（除了+） 都会被隐式转换成number
- 点之前的东西都被隐式转换成对象型

```javascript
	 (3.1415).toFixed(2)//"3.14"
	console.dir(3.1415)// undefined
```
- 数字运算符 ： + 一段是数字一段是字符串
- . 
- if语句 （条件部分）转换成布尔值
- ==
![Alt text](./1445363532717.png)
> 表达式 10-'2b' 的结果是NaN  
- 运算符+号转换
```html
<body>
10 + <input type="text" id="num"/><input type="button" value="等于" id="btn"/><span id="ret"></span>
<script type="text/javascript">
var btn = document.getElementById("btn");
var ret = document.getElementById("ret");
var num = document.getElementById("num");

btn.addEventListener('click',function(){
	ret.innerText = 10 + Number(num.value);//数字转换
})


</script>
</body>
```

###显示类型转换方法
- Number(),String(),Boolean()
- parseInt(),parseFloat() //字符串转换成数字
- !,!! //操作对象的布尔值

##类型识别

###typeof 重点
- 类型检查、识别类型
![Alt text](./1445408349506.png)

**总结**
- typeof可以识别标准类型（Null除外）
- 不能识别具体的对象类型（function除外）

###instanceof
###Object.prototype.toString.call
###constructor