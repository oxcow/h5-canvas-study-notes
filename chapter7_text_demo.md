# 示例代码

    var ctx = document.getElementById('test').getContext('2d');
    ctx.save();
    ctx.font = '40pt Times New Roman';
    ctx.textAlign = 'center';
    var textBaseline =['','top','hanging','middle','alphabetic','ideographic','bottom'];
    ctx.save();
    ctx.arc(400,200,100,0,2*Math.PI,true);//标记当前文字摆放位置
    ctx.mozTextStyle = "16pt bold sans serif";
    ctx.mozTextAlongPath(" S a m p l e S t r i n g",false);
    ctx.stroke();
    ctx.restore();
    for(var i=0;i<textBaseline.length;i++){
        ctx.save();
        //标记当前文字摆放位置
        ctx.arc(100+i*30,80,3,0,2*Math.PI,true);
        ctx.stroke();
        if(textBaseline[i]){
            ctx.textBaseline = textBaseline[i];
            ctx.fillText(i+1,100+i*30,80);
        }else{
            ctx.strokeText(i+1,100+i*30,80);
        }
        ctx.restore();
    }
    //标线
    ctx.moveTo(0,40);
    ctx.lineTo(500,40);
    ctx.stroke();
    ctx.moveTo(0,80);
    ctx.lineTo(500,80);
    ctx.stroke();
    ctx.moveTo(0,120);
    ctx.lineTo(500,120);
    ctx.stroke();
    
效果图：

![text demo](/images/text_demo.png)