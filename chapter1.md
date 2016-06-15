# Canvas 声明与获取

## Canvas Html 声明


    <canvas id="myCanvas" width="600" height="300"></canvas>

***Notes: *** 如果未指明 canvas 的宽和高，则默认为 300px 和 150px

## Canvas 对象获取

获取 CanvasRenderingContext2D 对象：

    var ctx = document.getElementById('canvas').getContext('2d');
