# rect方法

    rect(x, y, width, height)


绘制矩形路径。它接受四个参数。 x 和 y 为其矩形路径的左上角坐标。 width 和 height为其宽和高。 当它被调用时， moveTo 方法会自动被调用，参数为(0,0)，于是起始坐标又恢复成初始原点了