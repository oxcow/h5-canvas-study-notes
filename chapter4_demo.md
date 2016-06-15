# 示例代码

    ctx.save();
    // 画三角形
    ctx.beginPath();
    ctx.moveTo(75,50);
    ctx.lineTo(100,75);
    ctx.lineTo(100,25);
    ctx.fill();
    // 画圆
    ctx.beginPath();
    ctx.moveTo(180,150);
    ctx.arc(150,150,30,0,2*Math.PI,true);
    ctx.stroke();
    // 画弧
    ctx.beginPath();
    ctx.moveTo(200,150);
    ctx.arc(150,150,50,Math.PI * 3/4, Math.PI, true);
    ctx.stroke();
    //绘制贝塞尔曲线
    ctx.beginPath();
    ctx.moveTo(70,10);
    ctx.bezierCurveTo(50,50,50,90,70,20) ;
    ctx.stroke();
    //绘制二次方曲线
    ctx.beginPath();
    ctx.moveTo(10,150);
    ctx.quadraticCurveTo(100,180,50,150);
    ctx.stroke();
    //绘制矩形路径
    ctx.rect(120,50,100,40);
    ctx.stroke();
    ctx.restore();
    
效果图：

![drawing path demo](/images/chapter4_demo.png)