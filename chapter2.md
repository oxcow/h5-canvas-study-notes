# Canvas 状态保存与恢复


Canvas 的状态就是当前画面应用的所有样式和变形的一个快照；Canvas 状态是以栈
(stack)的方式保存的

## save方法

    save()
    
save 方法是用来保存 Canvas 状态的，没有参数。每一次调用 save 方法，当前的状态就会
被推入栈中保存起来。这种状态包括：

1. 当前应用的变形（即移动，旋转和缩放，见下）
strokeStyle, fillStyle, globalAlpha, lineWidth, lineCap, lineJoin, miterLimit, shadowOffsetX,
shadowOffsetY, shadowBlur, shadowColor, globalCompositeOperation 的值

2. 当前的裁切路径（clipping path）


## restore 方法

    restore()
    
 
restore 方法是用来恢复 Canvas 状态的，没有参数；每一次调用 restore 方法，上一个保存
的状态就从栈中弹出，所有设定都恢复