# 渐变 ( Gradients )

首先使用以下两个方法创建 ***canvasGradient*** 对象

    var gradientsColor = createLinearGradient(x1,y1,x2,y2)
    var gradientsColor = createRadialGradient(x1,y1,r1,x2,y2,r2)
    
然后给创建好的 ***canvasGradient*** 对象 *gradientsColor* 使用

    addColorStop(position,color)
    
进行上色。 上色晚上后将赋值给 **fillStyle** 或 **strokeStyle** 即可


## createLinearGradient方法

    createLinearGradient(x1,y1,x2,y2) 

该方法接受 4 个参数。 (x1,y1) 代表渐变的起始点，(x2,y2) 代表渐变的终点

## createRadialGradient方法

    createRadialGradient(x1,y1,r1,x2,y2,r2)

该方法接受 6 个参数。其中 (x1,y1,r1) 定义一个圆心坐标为 (x1,y1) 半径为 r1 的圆。 (x2,y2,r2) 定义一个圆心坐标为 (x2,y2) 半径为 r2 的圆。

## addColorStop方法

    addColorStop(position,color) 

方法接受 2 个参数。position 代表渐变中颜色的相对位置。取值为 [ 0.0 , 1.0 ]。例如 0.5 表示颜色出现于正中间； color 为一个有效的 CSS 颜色值

## 示例代码
### 示例一

    //沿 y 轴方向渐变。 (±∞,<=20)上为红色。 (±∞,>=80)上为绿色。 中间为渐变色
    var gradientsColor = ctx.createLinearGradient(0,20,0,80);
    //沿 x,y 轴夹角 45°渐变
    //var gradientsColor = ctx.createLinearGradient(20,20,80,80)
    gradientsColor.addColorStop(0,"rgb(255,0,0)"); // 红色
    gradientsColor.addColorStop(1,"rgb(0,255,0)"); // 绿色
    ctx.strokeStyle = gradientsColor;
    ctx.fillStyle = gradientsColor;
    ctx.fillRect(0,0,100,100);
    ctx.fill
    
效果图：

![Gradients Demo 1](/images/gradients_demo1.png)
### 示例二

    //圆(100,100,80)与圆(100,100,40)之间的圆环为渐变区域。 圆(100,100,80)外的区域
    //将为红色，而圆(100,100,40)内的部分将为绿色
    var gradientsColor = ctxd.createRadialGradient(100,100,80,100,100,40);
    //带有偏移的渐变色
    var gradientsColor = ctxd.createRadialGradient(100,100,80,130,130,30);
    gradientsColor.addColorStop(0,"rgb(255,0,0)"); // 红色
    gradientsColor.addColorStop(1,"rgb(0,255,0)"); // 绿色
    ctxd.strokeStyle = gradientsColor;
    ctxd.fillStyle = gradientsColor;
    ctxd.arc(100,100,100,0,2*Math.PI,true);
    ctxd.fill();
    
效果图：

![Gradients Demo 2](/images/gradients_demo2.png)

> Notes: 在使用 createRadialGradient 时，尽量避免两个员相交的情况出现，那样可能会出现意想不到的情况。

    var gradientsColor = ctx.createRadialGradient(100,100,80,130,130,50);
    ctx.lineWidth = 2; // 线宽
    gradientsColor.addColorStop(0,"rgb(255,0,0)"); // 红色
    //gradientsColor.addColorStop(0.6,"rgb (0,0,255)"); // 蓝色
    gradientsColor.addColorStop(1,"rgba(0,255,0,0.7)"); // 绿色
    ctx.strokeStyle = "blue"
    ctx.fillStyle = gradientsColor;
    //这里如果将半径设置为与createRadialGradient一样的80的话，则效果图
    //显示为(图3)
    ctx.arc(100,100,100,0,2*Math.PI,true);
    //下面三行代码只是为了比照其轮廓， 当渐变色所设定的圆相交时产生
    //的实际情况(图1)。注释去掉的话则为(图2)
    ctx.arc(100,100,80,0,2*Math.PI,true);
    ctx.arc(130,130,50,0,2*Math.PI,true);
    ctx.stroke();
    ctx.fill();

效果图：

![gradients demo 3](/images/gradients_demo3.png)