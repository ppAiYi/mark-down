# 图片上传
## 一. 跨域问题
* ### get
> 用get方式提交表单，参数拼接于地址栏中，数据量有限，不能提交大量数据，而且安全性不高。
* ### jsonp
> JSONP的实现原理就是创建一个script标签, 再把需要请求的api地址放到src里. 所以只能是GET的。
* ### post
> 用post方式提交，参数存在于请求体中，可以提交大量的数据，安全性可靠。
* ### iframe
> 创建一个隐藏的iframe，将form的target指向这个iframe，编写父窗口回调方法，供iframe子窗口调用（子窗口调父窗口方法）；与后端商定回调地址栏参数，form调用submit成功，后端会将定义好的参数，携带至iframe页面url后，触发子窗口方法，子窗口处理参数，调用父窗口方法传回需要的参数，即可实现跨越问题。

参考地址：
1. [iframe无刷新上传文件，回调](http://blog.csdn.net/niechangxu1994/article/details/50373505)

## 二. 图片压缩
* ### canvas
> 压缩图片不是直接把图片绘制到canvas，再调用toDataURL就行。<br/>需注意canvas使用问题，和IOS中，canvas绘制图片的限制：<br/>
> 1. IOS中，图片的大小，如果图片的大小超过两百万像素，图片也是无法绘制到canvas上的，调用drawImage的时候不会报错，但是你用toDataURL获取图片数据的时候获取到的是空的图片数据。<br/>
处理办法：瓦片绘制，即将图片分割成多块绘制到canvas上<br/>
> 2. IOS中，canvas的大小有限制，如果canvas的大小大于大概五百万像素（即宽高乘积）的时候，无法绘制。<br/>
处理办法：对图片宽高进行适当压缩<br/>
> 3. canvas的toDataURL是只能压缩jpg，当用户上传的图片是png的话，需要转成jpg，也就是统一用canvas.toDataURL('image/jpeg', 0.92)<br/>
> 4. 如果是png转jpg，绘制到canvas上，canvas存在透明区域，当转成jpg时透明区域会变成黑色，因为canvas的透明像素默认为rgba(0,0,0,0)，所以转成jpg就变成rgba(0,0,0,1)了，也就是透明背景会变成了黑色。<br/>
解决办法：绘制前在canvas上铺一层白色底。

参考地址：
1. [图片压缩](http://www.cnblogs.com/moqiutao/p/6279905.html)

## 三. 图片方向
* ### exif.js
> Exif.js 提供了 JavaScript 读取图像的原始数据的功能扩展，例如：拍照方向、相机设备型号、拍摄时间、ISO 感光度、GPS 地理位置等数据。<br/>
```
EXIF.getData(file, function() {
    EXIF.getAllTags(this);
    Orientation = EXIF.getTag(this, 'Orientation');
});
```
Orientation参数值是照片方向，根据它可以旋转得到照片
```
switch(Orientation){
    case 6://需要顺时针（向左）90度旋转
        context.translate(parseInt(realWidth/2),parseInt(realHeight/2));  
        context.rotate(0.5 * Math.PI);
        break;
    case 8://需要逆时针（向右）90度旋转
        context.translate(parseInt(realWidth/2),parseInt(realHeight/2));
        context.rotate(-0.5 * Math.PI);
        break;  
    case 3://需要180度旋转
        context.translate(parseInt(realWidth/2),parseInt(realHeight/2));
        context.rotate(Math.PI);
        break;  
}   
```

参考地址：
1. [exif.js API](http://code.ciaoca.com/javascript/exif-js/demo/)
2. [exif.js demo](http://blog.csdn.net/cdnight/article/details/46457241)
