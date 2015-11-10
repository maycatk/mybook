# 居中布局

```html
<div class="parent">
    	<div class="child">DEMO</div>
	</div>
```


##水平居中

1. ```inline-block + text-align```

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
2. ```table + margin```

```css
.child{
	display: table;
	margin: 0 auto;
}
/*只用设置一个属性，IE8也支持属性*/
/*兼容IE67 html换成table*/
```
3. ```absolute + transform```



