# 文本方法

## 度量字符 ( measureText )

    measureText(text)

该方法返回 text 字符在当前文本样式下的绘制时的像素宽度。返回对象为 TextMetrics。比如：

    var width = ctx.measureText('text').width;
    
将返回在当前文字样式下绘制'text'字符时的实际像素宽度。

## ~~度量字符 ( mozMeasureText )~~

    measureText(text)
    
使用方法同 measureText 方法。

> ***Notes:*** mozMeasureText 方法已被废弃，请参考使用 measureText 方法。

## 绘制填充字体 ( fillText )
    
    fillText(text,x,y,[optional] in float maxWidth)
    
添加 text 到指定位置。字体的大小样式由 font 属性决定；位置由 textAlign 属性决定；字体绘制基准线由textBaseline 属性决定； 字体填充由 fillStyle 属性决定； 但是strokeStyle 属性是被忽略的。

> ***Notes:*** 
> 
> (x,y)为文本做左上角的位置。因此在实际添加过程中要考虑文本字体的大小。maxWidth 为可选参数，用来声明绘制的最大宽度。