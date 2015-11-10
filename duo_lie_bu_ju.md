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

2015-11-10 22:11:11










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