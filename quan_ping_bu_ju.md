# 全屏布局

> 管理系统，后台管理，监控平台一般都是全屏布局

- 特点
撑满浏览器窗口
滚动条出现在主内容区域

---
![需求图](http://i13.tietuku.com/e594739669258a24s.png)

##实现方案

- Position
- Flex

### position

html结构

```html
<div class="parent">
		<div class="top">top</div>
		<div class="left">left</div>
		
		<div class="right">
		<div class="inner">right</div>
            <!-- 添加内容滚动 -->
        </div>
		<div class="bottom">bottom</div>
	</div>
```

css结构

```css
tml,body,.parent{height: 100%;overflow: hidden;}
.top{
	position: absolute;
	top: 0;
	left: 0;
	right: 0;
	height: 100px;
	background-color: grey;
}
.left{
	position: absolute;left: 0;top: 100px;bottom:50px;width: 200px;background-color: #ededed;
}
.right{
	position: absolute;
	overflow: auto; 
	/*设置滚动*/
	left: 200px;right: 0;top: 100px;bottom: 50px;background-color:#f7f7f7;
}
.bottom{
	position: absolute;left: 0;right: 0;bottom: 0;height: 50px;background-color: #d6d6d6;
}
.right .inner{
	min-height: 1000px;
}

/*IE6不兼容用HACK*/
```