#javascript程序设计

###在HTML中使用javascript

#### < script >元素

HTML页面中插入javascript的方法就是使用```<script>```标签；

两种使用方法：
- 页面中嵌入javascript代码

```html
<script type="text/javascript">
  function sayHi(){
    alert("HI!");
  } 
</script>
```
内部代码将被从上至下以次解释。

- 特例：
```html
<script type="text/javascript">
  function sayHi(){
    alert("</script>");
  } 
</script>
```
会出现错误，在javascript代码中任何地方都不要出现"</script>"字符串；解决方法：通过转义字符"\"；
```html
<script type="text/javascript">
  function sayHi(){
    alert("<\/script>");
  } 
</script>
```

---

- 包含外部javascript文件

```html
<script type="text/javascript" src="example.js"></script>
```
###一般javascript引用放在<body>页面内容后面

```html
<html>
<head>
	<meta charset="UTF-8">
    <title>实例</title>
</head>
<body>
	<!-- 页面内容 -->
	<script type="text/javascript" src="example.js"></script>
</body>
</html>
```











