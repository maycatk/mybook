# 优化页面

##减少请求
- 图片合并
 
- CSS文件合并
    - 多个CSS文件合并为一个
    - 少量css样式内联
    - 避免使用import的方式引入

- 减少文件大小
    - 减少图片大小
        - 选择合适的图片格式（PNG小图标JPG:banner色彩；）
        - 压缩图片
    - css值缩写
    - 省略值为0的单位
- 颜色值最短表示
    - 16进制缩写
- css选择器合并
- 文件压缩
   - YUI Compressor
   - cssmin

## 页面性能

css放head

js放body底部

- 减少标签数量