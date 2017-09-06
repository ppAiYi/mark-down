# C2C H5 项目总结v1
## 一. UI还原
1. 页面创建时，样式（大小，距离，颜色），需要与设计稿对照，避免后续样式修改过多

2. 设计稿，zeplin给出元素上下左右距离并不准确（行间距/padding/margin）

3. 兼容性：
* line-height在android部分机型未生效；

* border在retina屏，1px显示为2px问题；

* [flex布局的兼容性](http://blog.csdn.net/u010130282/article/details/52627661)
## 二. 通用组件
1. 通用css：如果样式通用，建议规定common.css文件，或组件定制化的css文件，引用组件时，不建议copy相同组件，修改样式，可以引用后覆盖样式；当覆盖样式达不到预期时，应改为局部样式，不再视为通用样式。</br>
目前页面引用样式复杂，维护较复杂；

2. 通用js：如时间格式化、cookies操作、请求等，需写入commonjs中，其他如页脚事件，表格事件等，应写入组件对应的js中，随组件共同引入；

3. css编码规范及书写规范（[BEM命名规范](http://www.cnblogs.com/dujishi/p/5862911.html)）

## 三. 项目结构
项目构层次不清晰，寻找问题根源不直截了当，需重构；目前结构，会影响开发效率、后期维护、迭代；

## 四. 项目上线
To continue to be……

## 五. 遗留问题
1. [图片上传问题](http://www.cnblogs.com/dujishi/p/5862911.html)
