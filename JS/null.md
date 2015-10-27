# Null

从逻辑角度来看，```null```值表示一个空对象指针；所以```typeof```操作符检测```null```值会返回```Object```
- 值：
  - null
- 出现场景
	- 表示对象不存在
	- var car = null;

---
保存对象的变量还没有真正保存对象，就应该明确让该变量保存null值，这样做不仅可以体现```null```作为空对象指针的惯例，也有助于进一步区分```null```和```undefined```


- 实际上undefined值是派生自null值:

```javascript
alert(undefined == null);//ture
```