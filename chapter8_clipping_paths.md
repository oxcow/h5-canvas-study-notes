# 裁切路径 ( Clipping paths )

裁切路径和普通的 Canvas 图形差不多，不同的是它的作用是遮罩，用来隐藏没有遮罩的部分。如右图所示。红边五角星就是裁切路径，所有在路径以外的部分都不会在 Canvas 上绘制出来

裁切路径和普通的 Canvas 图形差不多，不同的是它的作用是遮罩，用来隐藏没有遮罩的部分。如右图所示。红边五角星就是裁切路径，所有在路径以外的部分都不会在 Canvas 上绘制出来 ![clipping paths five star](/images/clipping_five_star.png)

如果和上面介绍的 globalCompositeOperation 属性作一比较，它可以实现与 source-in 和 source-atop 差不多的效果。最重要的区别是裁切路径不会在 canvas 上绘制东西，而且它永远不受新图形的影响。这些特性使得它在特定区域里绘制图形时相当好用。

## clip()

该方法来创建一个新的裁切路径。默认情况下， Canvas 有一个与它自身一样大的裁切路径（也就是没有裁切效果）

## 示例代码

    var ctx = document.getElementById('canvas').getContext('2d');
    ctx.fillStyle = 'rgba(0,0,0,0.2)';
    ctx.fillRect(0,0,200,200); // 绘制一个矩形区域
    ctx.beginPath();
    ctx.rect(0,0,200,200);
    ctx.clip(); // 制作一个大小为200*200的矩形裁剪区域
    ctx.save();
    //在裁剪区域内绘制一个圆(这个圆可以显示出来)
    drawArc(100,100,50,ctx);
    // 在裁剪区域边缘部分绘制一个圆(超出裁剪区域的部分将不会显示出来)
    drawArc(200,200,50,ctx);
    // 在裁剪区域外绘制一个圆，该圆无法显示
    drawArc(300,300,50,ctx);
    function drawArc(a,b,r,ctx){
        ctx.save();
        ctx.fillStyle = "rgba(100,50,200,0.8)";
        ctx.beginPath();
        ctx.arc(a,b,r,0,Math.PI * 2,true);
        ctx.fill();
        ctx.restore();
    }
    
效果图：

![clipping paths demo](/images/clipping_demo.png)