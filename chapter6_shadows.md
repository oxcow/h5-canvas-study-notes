# 阴影 ( Shadows )

## shadows 方法
实现阴影，需要设置以下四个属性

    shadowOffsetX = float
    shadowOffsetY = float
    shadowBlur = float
    shadowColor = float
    
**shadowOffsetX** 阴影在 X 轴的延伸距离，不受变换矩阵影响。负值表示阴影会往左延伸，正值表示向右延伸。默认值为 0

**shadowOffsetY** 阴影在 Y轴的延伸距离，不受变换矩阵影响。负值表示阴影会往上延伸，正值表示向下延伸。默认值为 0

**shadowBlur** 设定阴影的模糊程度，其数值并不跟像素挂钩，也不受变换矩阵影响。默认为 0

**shadowColor** 设定阴影效果的延伸，值可以是标准的 CSS 颜色值，默认为全透明的黑色

## 示例代码

    ctx.shadowOffsetX = 3;
    ctx.shadowOffsetY = 3;
    ctx.shadowBlur = 2;
    ctx.shadowColor = 'rgba(0,0,0,0.5))';
    ctx.font = "40px Times New Roman";
    ctx.fillStyle = "blue";
    ctx.fillText("Hello Canvas Shadow", 130, 140);

效果图：

![shadows demo](/images/shadows_demo.png)