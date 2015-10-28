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

###createElement
```var element = document.createElement(tag)```


| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| tag | String | 是 | 标签名 |
| element | Node |     |  |


> 实例：

```javascript
var element = document.createElement('span'); //创建span
element.textContent = 'This’s DOM'; //创建内容
```

###innerHTML
```element.innerHTML = HTMLString```

获取对象内容 **或者** 向对象插入内容

| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| HTMLString | String |  | 名 |
| element |  |     | 同步解析HTMLString为element dom树 |


> 实例：

html
```html
<html>
<body>
<div id="aa">this is a test!</div>
<div id="abc">ji</div>
</body>
</html>
```
js

```javascript
var i = document.getElementById('aa').innerHTML; //向id为aa的元素获取内容
alert(i); //输出
document.getElementById('abc').innerHTML='HOOOOO. THIS\'S ADD TEXT.';//向ID为abc添加内容
```

###innerHTML和createElement应用区别
- 节点个数
  - 多节点操作createElement创建复杂，用innerHTML只用一个字符串；
  
- 事件处理
  - createElement创建的节点可以直接添加事件，innerHTML只能通过在HTML添加onclick等事件（不推荐）或者添加事件委托来处理事件逻辑；
- 结合使用
- 实例：

```javascript
var tp1 = ' <div class="item">\
				<img class="j-flag"/>\
				<div class="j-flag"></div>\
			</div>';
var box = document.createElement('div');
box.innerHTML = tp1;
var list = box.getElementsByClassName('j-flag');
list[0].src = '/imgurl.jpg';
list[1].innerText = 'my name is netease';

```

##插入节点

- appendChild
- insertBefore
- insertAdjacentElement
- insertAdjacentHTML

### appendChild
```var child = parent.appendChild(child);```

| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| child | Node | 是 | 将节点插入到父节点最后子节点之后 |
| parent | Node |     | 父节点 |

> 实例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>innerHTML</title>
</head>
<body>
<p id="p">
	hello,
<span id="type">mooc</span>
users
<!-- appendChild -->
</p>
<script type="text/javascript" src="js.js"></script>
</body>
</html>
```

```javascript
var element = document.createElement('span');//创建标签
element.textContent = 'this is DOM';//添加标签内容
p.appendChild(element);//插入标签
```
### insertBefore

插入节点在父节点前面

```var newElm = parent.insertBefore(newElm,rElm);```

| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| newElm | Node | 是 | 将插入的节点 |
| rElm | Node |   是  | newElm将插入的之前节点 |
| parent | Node |   是  | 父节点 |

> 实例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>innerHTML</title>
</head>
<body>
<p id="p">
<!-- insertBefore -->
hello,
<span id="type">mooc</span>
users
</p>
<script type="text/javascript" src="js.js"></script>
</body>
</html>
```

```javascript
function $(id){
    return document.getElementById(id);
}//获取封装    
var element = document.createElement('span');
element.innerHTML = 'this is DOM'; 
var span = $('type');//获取Id为type的标签span
p.insertBefore(element,span);//在span插入element
```

### insetAdjacentElement

指定插入,根据参照节点插入节点


```var oElm = elm.insetAdjacentElement(sWhere,oElm);```

| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| sWhere | String | 是 | 位置描述（beforeBegin,afterBegin,beforeEnd,afterEnd） |
| oElm | Node |   是  | 插入节点 |
| elm | Node |   是  | 参照节点 |

> 实例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>innerHTML</title>
</head>
<body>
<!-- beforeBegin -->
<p id="p">
<!-- afterBegin -->
hello,
<span id="type">mooc</span>
users
<!-- beforeEnd -->
</p>
<!-- afterEnd -->
<script type="text/javascript" src="js.js"></script>
</body>
</html>
```

```javascript
var element = document.createElement('span');
element.innerHTML = 'this is DOM';
var span = $('type');
p.insertAdjacentElement('afterBegin',element);
```


### insetAdjacentHTML

指定插入,根据参照节点插入```字符串```
**不建议用此方法来插入节点**

```javascript
var str = '<span>this is dom</span>';
p.insertAdjacentElement('afterBegin',str);
```


####insetAdjacentElement 兼容方式实现

- 在老浏览器里面是不存在此API 创建兼容方法

```javascript
if (typeof HTMLElement!= "undefined" && !HTMLElement.prototype.insertAdjacentElement) {
	HTMLElement.prototype.insertAdjacentElement = function(where,parsedNode){
		switch(where){
			case 'beforeBegin':
				this.parentNode.insertBefore(parsedNode,this);break;
			case 'afterBegin':
				this.insertBefore(parsedNode,this.firstChild);break;
			case 'beforeEnd':
				this.appendChild(parsedNode);break;
			case 'afterEnd':
				if (this.nextSibling)
					this.parentNode.insertBefore(parsedNode,this.nextSibling);
				else
					this.parentNode.appendChild(parsedNode);
				break;
		}
	}
}
```

##修改节点
- innerHTML
- textContent(innerText) 火狐下没能实现这一属性

###innerHTML
- 万能的innerHTML

```javascript
elm.innerHTML = '<img src = 'a.png'/>'; // 添加
elm.innerHTML = '';//添加空
elm.innerHTML = '<ul><li>1</li><li>2</li></ul>';
elm.innerHTML += '<a href="http://www.ee.com">test</a>'; //新增内容达到修改节点内容
```
###textContene
- FF兼容

```javascript
HTMLElement.prototype._defineGetter_("innerText",function(){
	return this.textContent;
})
HTMLElement.prototype._defineSetter_("innerText",function(s){
	this.textContent = s;
})
```
###innerHTML VS innerText
```elm1.innerHTML = '<img src = "a.png"/>';```
直接产生图片,能出瞬间path成NODE树到页面上
```elm1.innerContent = '<img src = "a.png"/>';```
产生字符串

用```innerHTML```来修改内容会引起脚本的注入
> 一个攻击脚本被添加到网站上面就会通过脚本伪造cookie来获取用户信息

##删除节点
- removeChild
- replaceChild
- innerHTML 为空得方法来删除节点

### removeChild
```var child = parent.removeChild(child);```

| 参数名称 | 类型 | 是否必选 | 描述 |
| -- | -- | -- | -- |
| child | Node | 是 | 需要删除的节点 |
| parent | Node |   是  | child的父节点 |
| child | Node |   是  | 被删除的节点 |

- 实际使用中得封装使用

```javascript
function remove(elm){
	elm.parentNode.removeChild(elm);
}
```











