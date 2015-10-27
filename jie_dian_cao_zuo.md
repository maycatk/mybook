# 节点操作

> 本节内容概要
- getElementById,
- getElementsByClassName
- getElementsByTagName
- querySelector(All)
- createElement
- innerText
- appendChild
- insertBefore
- removeChild
- innerHTML

---

##获取节点

- getElementById
- getElementByClassName
- getElementByTagName
- querySelector

---

###getElementById
```javascript
var elm = document.getElementById(IDString);
```
| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| IDString | String | 是 | id字符串 |
| elm | Node |     | 被标记id为IDString的节点 |

- 封装function
```javascript
function $(id){
    return document.getElementById(id);
}
```
> 实例:

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>兼容版本元素遍历</title>
</head>
<body>
	<p id="p">hello,<span id="type">mooc</span> users </p>
	<div><img src="images/user.jpg"/>
	</div>
</body>
</html>
```
- 获取span标签 JS
```javasript
var type = document.getElementById('type');//未封装之前获取节点代码
var type = $('type');//封装后获取节点方法
```
###getElementsByClassName
```javascript
var collection = [elm|document].getElementsByClassName(classes);
```
> 在document中查找拥有classes的节点

| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| classes | String | 是 | 一个或多个样式(由空格分隔) |
| collection | HTMLCollection |     | live html collection |

> 实例:

获取两个```span```节点
```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<p>hello,<span class="flag">mooc</span>
		<span class="flag z-flag">users</span>
	</p>
</body>
</html>
```

```javascript
var list = p.getElementsByClassName('flag');
var type = list[0],user = list[1];//list[0] === "mooc",list[1] === "users"
var list1 = p.getElementsByClassName('flag z-flag');//获取第二个span方法
```

##未补完##

---

##创建节点
- createElement
- innerHTML


























