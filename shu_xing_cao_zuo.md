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