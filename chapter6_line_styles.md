# 线型 ( Line Styles )

> ***Notes:*** 以下针对线型的效果，均要在线宽为一定宽度时才能显示出来。如果 lineWidth 过
细则无法显示出所示效果。

## lineWidth 属性（ 线宽）

    lineWidth = value
    
设置当前绘线的粗细。 Value 必须为正值。默认 1.0

线宽是指给定路径的中心到两边的粗细。换句话说就是在路径的两边各绘制线宽的一半。因为画布的坐标并不和像素直接对应，当需要获得精确的水平或垂直线的时候要特别注意

想要获得精确的线条，必须对线条是如何描绘出来的有所理解。见下图，用网格来代表 canvas 的坐标格，每一格对应屏幕上一个像素点。在第一个图中，填充了 (2,1) 至 (5,5) 的
矩形，整个区域的边界刚好落在像素边缘上，这样就可以得到的矩形有着清晰的边缘。

![linewidth](/images/linewidth.png)

如果你想要绘制一条从 (3,1) 到 (3,5)，宽度是 1.0 的线条，你会得到像第二幅图一样的结果。实际填充区域（深蓝色部分）仅仅延伸至路径两旁各一半像素。而这半个像素又会以近似的方式进行渲染，这意味着那些 像素只是部分着色，结果就是以实际笔触颜色一半色调的颜色来填充整个区域（浅蓝和深蓝的部分）。这就是上例中为何宽度为 1.0 的线并不
准确的原因。

要解决这个问题，你必须对路径施以更加精确的控制。已知粗 1.0 的线条会在路径两边各延伸半像素，那么像第三幅图那样绘制从 (3.5,1) 到 (3.5,5) 的线条，其边缘正好落在像素边界，填充出来就是准确的宽为 1.0 的线条

## lineCap 属性（ 线段端点）

    lineCap = type
    
设置线段端点的形状。 type = butt | round | square。 默认 butt

    butt : 齐头。
    round : 半圆。 端点处加上了半径为一半线宽的半圆
    square : 矩形。 端点出加上了等宽且高度为一半线宽的方块
    
### 示例:

    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d');
        var lineCap = ['butt','round','square'];
        // Draw guides
        ctx.strokeStyle = '#09f';
        ctx.beginPath();
        ctx.moveTo(10,10);
        ctx.lineTo(140,10);
        ctx.moveTo(10,140);
        ctx.lineTo(140,140);
        ctx.stroke();
        // Draw lines
        ctx.strokeStyle = 'black';
        
        for (i=0;i<lineCap.length;i++){
            ctx.lineWidth = 15;
            ctx.lineCap = lineCap[i];
            ctx.beginPath();
            ctx.moveTo(25+i*50,10);
            ctx.lineTo(25+i*50,140);
            ctx.stroke();
        }
    }
    
效果图：

![lineCap demo](/images/lineCap_attr_demo.png)



## lineJoin 属性（ 线段连接点）

    lineJoin = type
    
设置两条线段的外侧边缘连接处的显示样子。 type = round | bevel | miter。默认 miter

    round : 圆弧连接。圆弧半径为线宽一半
    bevel : 直线连接。
    miter : 交叉连接。 交叉连接点受 miterLimit 属性影响

### 示例：

 
    function draw() {
        var ctx = document.getElementById('canvas').getContext('2d');
        var lineJoin = ['round','bevel','miter'];
        ctx.lineWidth = 10;
        for (i=0;i<lineJoin.length;i++){
            ctx.lineJoin = lineJoin[i];
            ctx.beginPath();
            ctx.moveTo(-5,5+i*40);
            ctx.lineTo(35,45+i*40);
            ctx.lineTo(75,5+i*40);
            ctx.lineTo(115,45+i*40);
            ctx.lineTo(155,5+i*40);
            ctx.stroke();
          }
      }

效果图：

![linejoin demo](/images/lineJoin_attr_demo.png)

**miterLimit** = value 线段外沿交点连接距离。线段夹角越小则 miter 所呈现的夹角外沿越大。当设置 miterLimit 的值小于原本自然的延伸交点时，呈现的结果将是 **bevel**。

miterLimit **默认值是 0**。

> ***Notes:*** 如果两条线段的自然外沿交点延伸值是 10，那么设置 **miterLimit** 为(0,10)， 将呈现 **bevel** 效果都是一样的。 这个属性算是鸡肋，当需要 bevel 效果时，可以直接设置 **lineJoin = bevel**

### 示例：

    var ctxd = document.getElementById('canvas').getContext('2d');
    ctxd.lineWidth = 15; // 设置线宽
    ctxd.miterLimit = 8;
    ctxd.moveTo(5,60);
    ctxd.lineTo(40,30);
    ctxd.lineTo(15,80)
    ctxd.stroke();
    
效果图：