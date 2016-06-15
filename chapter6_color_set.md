# 色彩设置 ( Color )

    fillStyle = Color 填充色
    strokeStyle = Color 轮廓色
    
其中

    Color = ‘rgb(0,0,0)’; // 三原色。
    Color = ‘rgba(0,0,0,0.1); //三原色、透明度。 a = [0,1] 0 为完全透明
    Color = ‘red’;
    Color = “#FFFFF”;

> ***Notes:*** 一旦设置了 **fillStyle** 或是 **strokeStyle**，那么后续所有图形绘制均使用该设置。如果需要设置不同颜色，则需要在绘图前重新设置色彩。