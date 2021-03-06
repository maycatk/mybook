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
/*优点，兼容性高，不支持table可以把结构改成table，inline-block可以加zoom:1*/
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
	transform:translate(-50%,-50%);
}

/*子元素对其他没有影响；缺点transform兼容性*/
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
综合解决

###课后讨论
水平列表的底部对齐
一个水平排列的列表，每项高度都未知，但要求底部对齐
```css
/*初始化*/
*{
    margin: 0;
    padding: 0;
    list-style: none;
}
/*li元素设置*/
.content li{
    text-align: center;
}
.l1{
    background: #B8E986;
    padding:50px 50px;
}
.l2{
    background: #F5A623;
    padding: 20px 50px;
}
.l3{
    background: #D0021B;
    padding: 40px 50px;
}
.l4{
    background: #BD10E0;
    padding:100px 50px;/*假定不定高度固定宽度*/
}
/*方法1：父元素设置flex + align-items:flex-end*/
.content{
    display: -webkit-flex;
    display: flex;
    align-items:flex-end;
}
/*优点：只用设置父元素；缺点：兼容性不行*/
/*方法2：设置display:table-cell*/
.content{
    text-align: center;
    display: table-cell;
    vertical-align: bottom;
    font-size: 0;/*消除空隙*/
 
}
.content li{
    display: inline-block;
}
/*兼容性较好，IE8也支持；IE67下可改用table结构，inline-block兼容用zoom:1*/
```


---

实现一个幻灯布局

![幻灯布局](http://i12.tietuku.com/ca3a12c44d90ffb0s.png)

已知结构如下：

```html
<div class="slide">
	<!-- 图片省略 -->
	<!-- 以下是指示器 -->
	<div class="pointer"><i></i><i></i><i></i></div>
</div>
```
要求如下：幻灯（slide）宽高未知，指示器（pointer）在底部且水平居中，距离底部10px，指示器中的圆直径为10px，个数未知，背景为黑色，间距为5px，请完成CSS。

```css
/*用定位的方法*/
.slide{
    height: 300px;
    background: #4A90E2;
    position: relative;
}
.pointer{
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform:translateX(-50%);
}
.pointer i{
    padding: 5px;
    margin-right: 5px;
    border-radius: 5px;//IE9以下不能兼容
    font-size: 0;//清除空隙
        background-color: black;
        cursor: pointer;
}
```