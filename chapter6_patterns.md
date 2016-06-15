# 图案 ( Patterns )

## createPattern 方法

    createPattern(image,type)
    
设置当前图片的展示效果。 image 可以是 Imag 对象或者其他 canvas 对象； type 可以为 repeat、 repeat-x、 repeat-y、 no-repeat 其中之一。

创建 pattern 后将其赋值给 fillStyle 或者 strokeStyle 即可。

> ***Notes:*** 在使用 createPattern 前，需要确保 Image 对象已经被加载。否则图片有可能显示效果不正确； FireFox 目前只支持 type=repeat，如果设置为 repeat-x | repeat-y 则效果仍然是 repeat 的效果。

## 示例代码
 
    var img = new Image();
        img.src = 'earth.png';
        img.onload = function(){
        var ptrn = ctx.createPattern(img,'repeat-y');
        ctx.fillStyle = ptrn;
        ctx.fillRect(0,0,600,300);
    }
    
效果图：