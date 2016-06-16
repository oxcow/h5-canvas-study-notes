# 暂停动画

一旦使用 setInterval 和 setTimeout 方法，动画帧将运动起来。为了让当前动画停止，我们可以使用 Javascirpt 中的

    clearTimeout(id_of_settimeout)
    
来暂停运动中的动画。id_of_settimeout 是调用 setInterval 或 setTimeout 方法的返回值。