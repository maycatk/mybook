# 多列布局

## 定宽 + 自适应


- float + margin

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