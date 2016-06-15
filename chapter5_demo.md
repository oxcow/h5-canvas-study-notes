# 示例代码

## 示例一
    var img3 = new Image();
    img3.src = 'earth.png';
    ctx.drawImage(img3,50,170,64,64); // 图片长宽增大1/2倍
    Author： LeeYee Blog： http://leeyee.iteye.com/ http://blog.csdn.net/oxcow/
    var img = new Image();
    img.src = 'earth.png';
    ctx.drawImage(img,128,128); // 图片原始大小
    var img2 = new Image();
    img2.src = 'earth.png';
    ctx.drawImage(img2,250,50,256,256); // 图片长宽增大2倍
    var img4 = new Image();
    img4.src = 'earth.png';
    
    // 裁剪图片的四分之一，起始点为图片的右下 1/4 处(64,64,64,64)， 如果是左上 1/4 的
    // 话坐标为(0,0,64,64);然后将图片放置在 Canvas 的 (50,50)处。这里不进行缩放。所
    // 以裁剪图片长宽保持 64px
    ctx.drawImage(img4,64,64,64,64,50,50,64,64);
    
效果图：

![dray image demo](/images/drawImage_image_demo.png)

## 示例二

    <canvas id="ca1"></canvas><canvas id="ca2"></canvas>
    var img = document.getElementById("ca1"); // 将id="ca1"的cavans作为图片
    var ctx2 = document.getElementById("ca2").getContext("2d");
    ctx2.drawImage(img,100,100);