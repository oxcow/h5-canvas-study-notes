# rotate 方法（旋转）

    rotate(angle)
    
`rotate()` 方法通过指定一个角度，改变了画布坐标和 Web 浏览器中的 `<Canvas>` 元素的像
素之间的映射，使得任意后续绘图在画布中都显示为旋转的。它并没有旋转 `<Canvas>` 元素
本身。


***Notes: ***这个角度是用弧度指定的。如需把角度转换为弧度，请乘以 Math.PI 并除以 180。


    ctx.rotate(-Math.PI/4); //逆时针旋转 45°

变换后的实际坐标如图中的虚线所示位置 

![rotate](/images/rotate.png)