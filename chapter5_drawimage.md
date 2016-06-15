# drawImage 方法

## 基本方法

    drawImage(image,x,y)
    
放置图片对象 image 到指定的坐标(x,y)处

## 缩放方法
    drawImage(image,x,y,width,height)
    
放置图片对象 image 到坐标(x,y)处，并且图片区域大小为(width,height)，如果图片实际大小比(width,height)大，则放大图片，否则缩小图片

## 切片方法

    drawImage(image, sx, sy, sWidth, sHeight, dx, dy, dWidth, dHeight)

在原始图片 image 上裁剪大小为(sWidth,sHeight)大小的子图片，裁剪起点位于原始图片的(sx,sy)处。然后将裁剪区域得字图片放置在 Canvans 的(dx,dy)处大小为(dWidth,dHeight)。

(sx, sy, sWidth, sHeight) 原图片需要被裁剪的部分。

(sx, sy) 图片裁剪区坐标起始点；

(sWidth, sHeight) 裁减大小

(dx, dy, dWidth, dHeight) 裁剪获取部分图片的在canvas上的显示位置