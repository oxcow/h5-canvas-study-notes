# 示例代码

一个简单的运动的方块。

    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
    "http://www.w3.org/TR/html4/loose.dtd">
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>jQuery Snake</title>
    <style type="text/css">
    body {
        background: #eeeeee;
    }
    canvas {
        border: 1px solid gray;
    }
    </style>
    <script type="text/javascript">
        var Block = {
            X : 0,
            Y : 0,
            TimeClock : null
        }
        function test() {
            var ctx = document.getElementById('test').getContext('2d');
            ctx.save();
            ctx.clearRect(0,0,600,400);//清理画布
            ctx.translate(Block.X,Block.Y);
            ctx.fillRect(0,0,10,10);
            if(Block.Y <= 380){
                Block.X += 10;
                Block.Y += 10;
            }
            ctx.restore();
        }
        function start(){// 开始
            Block.TimeClock = setInterval(test, 800);//0.8秒
        }
        function stop(){//暂停
            if(Block.TimeClock){
                clearTimeout(Block.TimeClock);
            }
        }
    </script>
    </head>
    <body>
        <canvas id='test' width='600' height="400"></canvas>
        <button onclick="start();">start</button>
        <button onclick="stop();">stop</button>
    </body>
    </html>
    

效果图：[^comment]

![carton demo: a move block](/images/carton_demo.png)

[^comment]: 这是个动态图。可以保存代码为html，然后在浏览器中打开查看效果