# 表单操作
###select
- 级联下拉选择器
   - onchange
   - remove
   - add
```javascript
function fillSelect(select,list){
    for(var i = select.length -1;i>0;i--){
        select.remove(i);//倒序遍历    
    }
    list.forEach(funciton(data){
        var option = new Option(data.text,data.value);
        select.add(option);//添加属性
    });
}
fillSelect(chapterSelect,chapters);//章的数据去填充章的选择器

chapterSelect.addEventListener(
    'change',fucntion(event){
        var value = event,target.value,
            list = sections[value]||[];
        fillSelect(sectionSelect,list);//当有变化时填充
    }
);
```