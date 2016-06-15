# 矩形 ( Rectangles )

绘制矩形可以使用下述三个方法

    fillRect(x,y,width,height) 绘制一个填充的矩形
    strokeRect(x,y,width,height) 绘制一个未经填充的矩形
    clearRect(x,y,width,height) 清理出一块矩形区域
    
其中参数 x,y 均指所绘制矩形的左上角坐标位置（相对坐标原点）。 width、 height 为矩形的宽和高。

> ***Notes:*** 在使用上述方法时，绘制出的图形会立即显示在 Canvas 上。


## 示例代码

    //绘制 200*200 的矩形
    ctx.fillRect(90,90,200,200);
    //在上述矩形中清除一块160*160的矩形面积
    ctx.clearRect(110,110,160,160);
    //在清除的矩形面积中绘制 100*100的矩形边框
    ctx.strokeRect(140,140,100,100);
    
![rect_demo1](/images/rect_demo1.png)