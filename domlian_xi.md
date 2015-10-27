# DOM练习

1.如何实现浏览器兼容版的element.children
> element.children能够获取元素的元素子节点，但是低版本的ie不支持，如何在低版本的ie上兼容类似的功能。

```javascript
function getElementChildren(element){
	if (!element.children){//判断当前浏览器有无element.children方法
		var elementArr = []; //如果没有创建一个数字进行存储
		var nodeList = element.childNodes;//获取参数字节点的集合
		for (var i = 0; i < nodeList.length; i++) {//循环遍历子节点数组
			if (typeof nodeList[i] == 1) { //判断当前子节点是否为元素类型
				elementArr.push(nodeList[i]);	
			}
		}
		return elementArr;  //返回值
	}else{
		return element.children;
	}
}

```
