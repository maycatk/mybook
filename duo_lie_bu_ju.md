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

11-10 22:11:11












