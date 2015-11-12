# 多列布局

## 定宽 + 自适应


- float + margin

优点：容易理解

缺点：IE7以下有兼容问题 在IE6上面会有3PX bug；在```.left```css里面加上 ```padding-right:-100px;``` hack;两个元素都有浮动 子元素p如果清除浮动会有BUG 文字会掉位置；

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>多列布局</title>
	<style type="text/css">
*{margin:0;padding: 0;}
.left{float: left;width: 100px;background: #ececec;}
.right{margin-left:120px;background: #bababa;}
	</style>
</head>
<body>
	<div class="parent">
		<div class="left">
			<p>left</p>
		</div>
		<div class="right">
			<p>right</p>
			<p>right</p>
		</div>
	</div>
</body>
</html>
```
- 改进方案

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>多列布局</title>
	<style type="text/css">
*{margin:0;padding: 0;}
.left{float: left;width: 100px;background: #ececec;position:relative;} /*提高层级*/
.right-fix{float: right;width: 100%;margin-left: -100px;} /*hack使得清除浮动后没有BUG*/
.right{margin-left:120px;background: #bababa;}
	</style>
</head>
<body>
	<div class="parent">
		<div class="left">
			<p>left</p>
		</div>
		<div class="right-fix"> //增加一个容器结构
			<div class="right">
				<p>right</p>
				<p>right</p>
			</div>
		</div>
	</div>
</body>
</html>

```
- folat + overflow

```css
.left{
    float: left;
    width: 100px;
    margin-left: 20px;
    background: red;
}
.right{
    overflow: hidden;
    /*ie6不支持*/
    background: blue;
}
```
- table

```css
.parent{
    display: table;
    width: 100%;
    table-layout: fixed;

    /*实现布局优先，加速table渲染*/

}
.right{
    background: blue;

}
.left,.right{
    display: table-cell;    
}
.left{
    width: 100px;
    padding-right: 20px;
    background: red;
}
```

> 这个方法并没有什么卵用，padding-right下left内容空隙还是和background融合了；

- flex

```css
.parent{
    display: flex;
    /*宽度自动跟着内容走*/
}
.right{
    flex:1;
    background: blue;

}
.left{
    width: 100px;
    margin-right: 20px;
    background: red;
}
/*兼容性，flex是根据内容做改动；一般使用在小范围布局中*/
```

### 多列定宽一列自适应

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>testhtml</title>
    <style type="text/css">
.left,.center{
    float: left;
    width: 100px;
    margin-right: 20px;
    background: blue;
}
.right{
    overflow: hidden;
    background: red;
}

    </style>
</head>
<body>
    <div class="parent">
        <div class="left">
        <p>left</p>
        </div>
        <div class="center">
            <p>center</p>
        </div>
        <div class="right">
            <p>right</p>
            <p>right</p>
        </div>
    </div>
</body>
</html>
```

### 不定宽+自适应

- float+overflow

```css
.left{
    float: left;
    width: 100px;
    margin-left: 20px;
    background: red;
}
.right{
    overflow: hidden;
    /*ie6不支持*/
    background: blue;
}
```

- table

```css
.parent{
    display: table;
    width: 100%;
    /*实现布局优先，加速table渲染*/

}
.right{
    background: blue;

}
.left,.right{
    display: table-cell;    
}
.left{
    width:0.1%;
    <!-- 可以不定宽 -->
    padding-right: 20px;
    background: red;
}
.left p{
    width:200px;
    <!-- left由内容决定宽度 -->
}
```
- flex

```css
.parent{
    display: flex;
    /*宽度自动跟着内容走*/
}
.right{
    flex:1;
    background: blue;

}
.left{
    margin-right: 20px;
    background: red;
}
.left p{
    width:200px;
    <!-- 宽度跟着内容 -->
}
```
### 不定宽+不定宽+自适应

```css
.left,.center{
    float: left;
    margin-right: 20px;
    background: blue;
}
.right{
    overflow: hidden;
    background: red;
}
.left p,.center p{
    width: 100px;
    /*内容决定*/
}
```
### 等分布局
![等分布局](http://i13.tietuku.com/abafe22a9bda4ad4s.png)

公式：$$C + G=(W+G)*N$$

- float

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>testhtml</title>
	<style type="text/css">
.parent{
	margin-left: -20px;
}
.coulumn{
	float: left;
	width: 25%;
	padding-left: 20px;
	box-sizing: border-box;
}
/*兼容性可以IE8以上，缺点不同列要修改css*/
	</style>
</head>
<body>
	<div class="parent">
	    <div class="coulumn"><p>1</p></div>
	    <div class="coulumn"><p>2</p></div>
	    <div class="coulumn"><p>3</p></div>
	    <div class="coulumn"><p>4</p></div>
	</div>
</body>
</html>
```

- table

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>testhtml</title>
	<style type="text/css">
.parent-fix{
	margin-left: -20px;
}
.parent{
	display: table;
	width: 100%;
	table-layout: fixed;
	/*1.布局优先；2.单元格宽度默认平分*/
}
.coulumn{
	display: table-cell;
	padding-left: 20px;
}
/*不管多少列都可以平分，缺点是修改html框架*/
	</style>
</head>
<body>
<div class="parent-fix">
	<div class="parent">
	    <div class="coulumn"><p>1</p></div>
	    <div class="coulumn"><p>2</p></div>
	    <div class="coulumn"><p>3</p></div>
	    <div class="coulumn"><p>4</p></div>
	</div>
</div>
<!-- 添加修改增加20px；框架 -->
</body>
</html>
```
- flex


```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>testhtml</title>
	<style type="text/css">
*{
	margin:0;
	padding: 0;
}
.parent{
	display: flex;
}
.coulumn{
	flex:1;
	background-color: pink;
}
.coulumn+.coulumn{
	/*一个coulumn下面的column*/
	margin-left: 20px;
}
/* 除了浏览器兼容性差 其他很完美 */
	</style>
</head>
<body>
	<div class="parent">
	    <div class="coulumn"><p>1</p></div>
	    <div class="coulumn"><p>2</p></div>
	    <div class="coulumn"><p>3</p></div>
	    <div class="coulumn"><p>4</p></div>
	</div>
</body>
</html>
```






## 课后讨论

- 一个全等四宫格的实现
一个未知宽高的容器，要被均分为四个相同大小格子（即四个容器），且格子间有10px间距（即十字型空隙）

![格子](http://img0.ph.126.net/5XU_Ds_5SRehh_15MCbCjQ==/2450802622237686522.png)




---

- 实现一个自适应布局

按要求完成能兼容所有浏览器的HTML和CSS：一个不定宽度的容器被分为左中右三列，左右两列定宽100px，中间列自适应剩余宽度，且三列之间间距为10px

![自适应布局](http://img1.ph.126.net/CmctGQgqoxz51SjXdGw3-Q==/6630878649699201619.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>实现一个自适应布局</title>
	<style type="text/css">
*{margin:0;padding: 0;}
.content{
	width: 100%;
	margin: 0 auto;
	background: red;
	text-align: center;
}
.left{
	float: left;
	width: 100px;
	background: #ff0;
	position: relative;
}
.main-fix{
	float: left;
	margin-left: -100px;
	margin-right: -100px;
	width: 100%;
}
.main{
	background:pink;
	margin:0 120px;
}

.right{
	float: right;
	width: 100px;
	background: blue;
}
	</style>
</head>
<body>
	<div class="content">
		<div class="left">左侧定宽</div>
		<div class="main-fix">
		<div class="main">中间自适应</div>
		</div>
		<div class="right">右侧定宽</div>
	</div>
</body>
</html>
```