# moveTo方法

    moveTo(x,y)
    
移动到某一坐标点。 x、 y 为移动目标坐标。

> ***Notes:*** 虽然 Canvas 初始化或者调用 beginPath 的时候，起始坐标是设置在圆点(0,0)，但在绘制路径的时候，如果需要回到原点，还是需要调用 moveTo 方法显示的指明。 如果直接调用 lineTo 方法会导致实际无法显示的结果。 比如如下代码：
>
        ctx.beginPath();
        ctx.moveTo(0,0);
        ctx.lineTo(100,100);
        ctx.closePath();
        ctx.stroke();
        
> 当将 ctx.moveTo(0,0)注释掉时，实际上是无法绘制出一条直线的，虽然 ctx.beginPath()默认设置当前点是原点。