# 居中布局

```html
<div class="parent">
    	<div class="child">DEMO</div>
	</div>
```


##水平居中

- ```inline-block + text-align```

```css
child{
	display: inline-block; /*根据内容增加宽度*/

}
.parent{
    text-align: center;
}
/*兼容性比较好，在IE67下display：inline-block;加zoom:1*/
/*缺点，child会继承到text-align:center;child不需要居中的话，需要加一句text-align:left;*/
```
- ```table + margin```

```css
.child{
	display: table;
	margin: 0 auto;
}
/*只用设置一个属性，IE8也支持属性*/
/*兼容IE67 html换成table*/
```
- ```absolute + transform```

```css
.parent{
	position: relative;
}
.child{
	position: absolute;
	left: 50%;
	transform:translateX(-50%);
}
/*子元素不会对其他元素产生影响*/
/*缺点transform是CSS3新属性，兼容性不行*/
```
- ```flex + justify-content```

```css
.parent{
	display: flex;
	justify-content:center; 
}

/*优点，只用设置父元素*/
```
```css
.parent{
	display: flex;
}
.child{
	margin: 0 auto;
}
/*同样的效果*/
```

缺点```flex```在IE678不支持

---

##垂直居中
```html
<div class="parent">
    	<div class="child">DEMO</div>
	</div>
```

- ```table-cell + vertical-align```

```css
.parent{
    display: table-cell;
    vertical-align:middle;
}
/*兼容性比较好IE8也支持，支持67 html换成table*/
```
- ```absolute + transform```

```css
.parent{
    position:relative;
}
.child{
    position:absolute;
    top:50%;
    transform:translateY(-50%);
}
```
- ```flex + align-items```

```css
.parent{
    display:flex;
    align-items:center;
}
/*只需要给父元素设置元素 缺点是兼容性/
```
---

##居中


- ```inline-block + text-align + table-cell + vertical-align```

```css
.parent{
	text-align: center;
	display: table-cell;
	vertical-align: middle;
}
.child{
	display: inline-block;
}
/*优点，只用设置父元素；缺点兼容性不高*/
```
- ```absolute + transform```

```css
.parent{
	position: relative;
	
}
.child{
	position: absolute;
	left: 50%;
	top: 50%;
	transform:translate(-50%,50%);
}

/*子元素对其他没有影响；缺点兼容性不高*/
```
- ```flex + justfy-content + align-items```

```css
.parent{
	display: flex;
	justify-content:center;
	align-items:center;
}
/*优点，只用设置父元素；缺点兼容性不高*/
```
##总结
熟悉CSS各个布局属性特性
分解问题
综合