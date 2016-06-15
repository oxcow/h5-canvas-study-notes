# arc方法

    arc(x,y,radius,startAngle,endAngle,anticlockwise)
    
绘制弧线或者圆。其中 x,y,radius 依次为圆心 X 轴坐标、 Y 轴坐标及圆的半径。 startAngle 和
endAngle 分别是起末弧度（以 x 轴为基准）， anticlockwise 为 true 表示逆时针，反之顺时
针

> **Warning:** 在 Firefox 的 beta 版本里，最后一个参数是 clockwise， 而最终版本不是。因此如果是从 beta 升级至发行版需要做相应修改


> ***Notes:*** arc 方法里用到的角度是以弧度为单位而不是度。度和弧度直接的转换可以用这个表达式： **`var radians = (Math.PI/180)*degrees;`**