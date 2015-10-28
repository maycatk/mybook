# 属性操作
##HTML attribute -> DOM property
![属性转换](http://i13.tietuku.com/be037c974dcc8fefs.png)

- property accessor
- getAttribute/setAttribute
- dataset

##property accessor 属性访问器
- 读

```html
<div>
	<label for="userName">用户名:</label>
	<input type="text" id="userName" class="u-text">
</div>

```
```javascript
input.className;//"u-text"
input["d"];//"userName"
```
- 写

```html
<div>
	<label for="userName">用户名:</label>
	<input type="text" id="userName" class="u-text">
</div>

```

```javascript
input.value = 'wwq@155.com';//写操作
```
## 属性类型
![属性类型](http://i13.tietuku.com/8c6fffed49c2aeb4s.png)

转换过的实用对象

- 用属性访问器访问
通用性差 - 名字异常
扩展性差
实用对象

##getAttribute/setAttribute 属性访问符
- 读

```var attribute = element.getAttribute(attributeName); ```

实例：

```html
<div>
	<label for="userName">用户名:</label>
	<input type="text" id="userName" class="u-text">
</div>
```

```javascript
input.getAttribute("class");//"u-text"
```

- 写
```element.setAttribute(name,value);```

```html
<div>
	<label for="userName">用户名:</label>
	<input type="text" id="userName" class="u-text">
</div>
```

```javascript
input.setAttribute("value","ww2@qrf.com");//"u-text"
```
- 他们获取的都是属性字符串
- 用get\*\*\*操作仅字符串
- 通用性


##dateset

- HTMLElement.dataset
- data-*属性集
- 元素上保存数据

一般用来做自定义的属性
![](http://i13.tietuku.com/21b389656181d21fs.png)


[点击查看实际用例](http://codepen.io/maycatk/pen/MaGOwV)

