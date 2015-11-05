# 表单操作
###select
- 级联下拉选择器
   - onchange
   - remove
   - add
```javascript
function fillSelect(select,list){
    for(var i = select.length -1;i>0;i--){
        select.remove(i);    
    }
}

```