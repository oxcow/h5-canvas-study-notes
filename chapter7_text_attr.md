# 文本属性

## 字体设置 ( font )

    font()

设置字体大小及样式。比如

    ctx.font = "40px Times New Roman";


## 字体位置 ( textAlign)

    textAlign()

设置字体的位置。有 5 个属性，分别是： left、 light、 center、 start 及 end。比如：

    ctx.textAlign = 'center';
    
## 字体绘制基线 ( textBaseline)

    textBaseline()

设置渲染文字时的基线。 

    ctx.textBaseline = 'top';
    
有 6 个属性，分别是 *top*、 *hanging*、 *middle*、 *alphabetic*、 *ideographic* 及 *bottom*。其中**默认值为 alphabetic**，当前**不支持** **hanging**、 **ideographic**，如果设置为 hanging 其效果将为默认值效果。具体效果请看示例。