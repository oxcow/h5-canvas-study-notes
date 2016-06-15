# 引入图片

## 引入页面内部图片

    <img id= „imgId‟ src=”example.jpg”/>
    var img = document.imags[0];
    var img = document.getElementById(“imgId”)
    var img = document.getElementByTagName(“img”)[0];
    
## 引用其他 Canvas 作为图片

    <canvas id=‟canvasId‟></canvas>
    var img = document.getElementById(„canvasId‟);// 注意被引用canvas的不能为动态图像

## 创建新图片

    var img = new Imag();
    img.src = “example.png”;

## 通过 data:url 嵌入图片

    var img ='data:image/gif;base64,R0lGODlhCwALAIAAAAAA3pn/ZiH5BAEAAAEALAAAAAALAA
    sAAAIUhA+hkcuO4lmNVindo7qyrIXiGBYAOw==';