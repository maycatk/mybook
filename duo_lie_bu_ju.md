# 多列布局

## 定宽 + 自适应


- float + margin

优点：容易理解
缺点：IE7以下有兼容问题 在IE6上面会有3PX bug；在```.left```css里面加上 ```padding-right:-100px;``` hack;两个元素都有浮动 子元素p如果清除浮动会有BUG
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>多列布局</title>
	<style type="text/css">
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