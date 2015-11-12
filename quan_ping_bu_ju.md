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
		<div class="right">right</div>
		<div class="bottom">bottom</div>
	</div>
```