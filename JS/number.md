# Number

- 整数
	- 15
	- var num = 10;
	- 0377 八进制 ```八进制在严格模式下无效```
	- 0xff   十六进制
- 浮点数 ```最高精度为17位小数```
	- 1.2
	- var num - 3.1416
	- 1.4E2 == $$1.4e^2$$ == $$1.4*10^2$$
	- 浮点运算存在舍入误差；
	```0.1加0.2结果不是0.3而是0.300000000000000004```
- 特殊值
	- NaN(Not a Number)
	- Infinity 无穷大
- 数值范围
  - 最大值：```5e-324```
  - 最小值：```1.7976931348623157e+308```
  - 超出范围的值会被转换成特使的```Infinity```值；负数为```-Infinity```(负无穷)；正数为```+Infinity```(正无穷);

检测一个数值是否超范围:

```javascript
  var result = Number.MAX_VALUE + Number.MAX_VALUE;
  alert(isFinite(result));//false 超出范围
```