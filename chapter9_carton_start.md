# 开始动画

动画每一帧的制作完成后，就需要将这些帧按一定的顺序组织，然后使其运动起来。一般我们会用到 Javascript 中的

    setInterval(animateShape,time)
    setTimeout(animateShape,time)
    
来操控动画。其中 animateShape 为绘制帧的方法， time 是条用绘制帧方法的时间间隔。这两个方法的区别在于。 


1. *setInterval* 方法是设定**每 time 秒执行一次** animateShape 方法
2. *setTimeout* 是 **time 秒后开始执行** animateShape 方法，只执行一次。


因此一般上我们需要使用 *setInterval* 方法来实现动画帧的连续。