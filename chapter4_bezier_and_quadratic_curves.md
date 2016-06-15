# 二次方曲线和贝塞尔曲线 ( Bezier and quadratic curves)

![bezier and quadratic curves](/images/drawimage_bezier.png)


    bezierCurveTo(cp1x,cp1y,cp2x,cp2y,x,y) 绘制贝塞尔曲线
    quadraticCurveTo(cp1x,cp1y,x,y) 绘制二次方曲线

上面两行代码的区别见图。它们都有一个起点一个终点（图中的蓝点），但二次方贝塞尔曲线只有一个（红色）控制点点）而三次方贝塞尔曲线有两个参数 x 和 y 是终点坐标， cp1x 和 cp1y 是第一个控制点的坐标， cp2x 和 cp2y 是第二个的