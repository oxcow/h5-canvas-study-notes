# save方法

save 方法是用来保存 Canvas 状态的，没有参数。每一次调用 save 方法，当前的状态就会
被推入栈中保存起来。这种状态包括：

1. 当前应用的变形（即移动，旋转和缩放，见下）
strokeStyle, fillStyle, globalAlpha, lineWidth, lineCap, lineJoin, miterLimit, shadowOffsetX,
shadowOffsetY, shadowBlur, shadowColor, globalCompositeOperation 的值

2. 当前的裁切路径（clipping path）

