# 文本方法

## 度量字符 ( measureText )

    measureText(text)

该方法返回 text 字符在当前文本样式下的绘制时的像素宽度。返回对象为 TextMetrics。比如：

    var width = ctx.measureText('text').width;
    
将返回在当前文字样式下绘制'text'字符时的实际像素宽度。

## ~~度量字符 ( mozMeasureText )~~

    measureText(text)
    
使用方法同 measureText 方法。

> ***Notes:*** 
> 
> mozMeasureText 方法已被废弃，请参考使用 measureText 方法。

## 绘制填充字体 ( fillText )
    
    fillText(text,x,y,[optional] in float maxWidth)
    
添加 text 到指定位置。字体的大小样式由 font 属性决定；位置由 textAlign 属性决定；字体绘制基准线由textBaseline 属性决定； 字体填充由 fillStyle 属性决定； 但是strokeStyle 属性是被忽略的。

> ***Notes:*** 
> 
> (x,y)为文本做左上角的位置。因此在实际添加过程中要考虑文本字体的大小。maxWidth 为可选参数，用来声明绘制的最大宽度。

## 绘制字体 ( mozDrawText )
    
    mozDrawText(text)
    
绘制通过 mozTextStyle属性声明的文本。文本的填充色为当前上线文中设置的填充色。比如：
    
    ctx.translate(10,50);
    ctx.fillStyle = 'red';
    ctx.mozDrawText('test mozDrawText');
    
> ***Notes:*** 
> 
> mozDrawText 方法在官方的 html5 中为过时方法，请参考使用 fillText 方法和strokeText 方法。

## 绘制字体 ( mazPathText )

    mazPathText(text)
    
添加指定文字 text 笔画到当前路径。假如你愿意，允许你使用文字比画替代文字填充。比如：
    
    ctx.translate(200,200);
    ctx.strokeStyle = "black";
    ctx.mozPathText("Sample String");
    
## 绘制字体 ( mazTextAlongPath )

    mazTextAlongPath (text,stroke)
    
添加指定文字 text 笔画到当前路径。假如你愿意，允许你使用文字比画替代文字填充。对于stroke 参数，如果声明为true，则文本将沿着声明的路径进行绘制；如果声明为 false，则文本将沿着当前的路径进行绘制。 如下代码
    
    ctx.save();
    ctx.arc(400,200,100,0,2*Math.PI,true);
    ctx.mozTextStyle = "16pt bold sans serif";
    ctx.mozTextAlongPath(" S a m p l e S t r i n g",false);
    ctx.stroke();
    ctx.restore();
    
将绘制出：

![mazTextAlongPath demo](/images/mazTextAlongPath_demo.png)

## 绘制字体轮廓 ( strokeText )

    strokeText(text,x,y,[optional] in float maxWidth)
    
该方法同 fillText，只不过该方法绘制出的字体没有进行填充。