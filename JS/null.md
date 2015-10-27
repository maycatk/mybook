# Null

从逻辑角度来看，```null```值表示一个空对象指针；所以```typeof```操作符检测```null```值会返回```Object```
- 值：
  - null
- 出现场景
	- 表示对象不存在
	- var car = null;

---

- 实际上undefined值是派生自null值:

```javascript
alert(undefined == null);//ture
```