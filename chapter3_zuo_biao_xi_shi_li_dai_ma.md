# 示例代码

## 示例一

    ctx. rotate(-Math.PI/2); // 逆时针旋转坐标轴 90°
    ctx.translate(-600, 0); // 转换坐标系

或者

    ctx.translate(0, 600);
    ctx.rotate(-Math.PI/2);

![cood_demo1](/images/cood_demo1.png)

## 示例二

    ctx.scale(1, -1); // 相对X轴对折Y轴
    ctx.translate(0, -600); // Y 轴下移
    
或者

    ctx.translate(0, 600);
    ctx.scale(1, -1);
    
![cood_demo2](/images/cood_demo2.png)    
    
示例三

    ctx.scale(1, -1); // Y轴旋转180°
    ctx.translate(0, -600); // Y 轴垂直向上偏移 600
    
或者

    ctx.translate(0, 600); // Y轴垂直向下偏移600
    ctx.scale(1, -1); // Y轴旋转180°

![cood_demo3](/images/cood_demo3.png)