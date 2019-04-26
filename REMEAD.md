# canvas 使用文档
## canvas的起步
- 如何在canvas 上使用绘图第一个vans图呢？ 
    - 第一步： 需要获取canvas `var canvas = document.querySelect('canvas')` 
    - 第二步： 需要创建画布 `var ctx = canvas.getContext('2d')`此方式也称为获取上下文
    - 第三步： 绘制画图的起点 `ctx.moveTo(10,20)` 也可以称为移动画笔吧 
    - 第四步： 绘制路径`ctx.lineTo(100,20)`
    - 第五步： 填充路径（也叫描边） `ctx.stroke()`
## canvas绘图注意事项
- 首先需要注意的是  `canvas`只有width和height两个属性。canvas默认的宽高是300X150。 如果需要设置新的宽高，这需要在行内写出样式如： `<canvas widht=400 height=300  id="canvas"></canvas>` 这样设置canvas的宽高不会导致canvas的图像变形。如果使用style设置宽高，则可能出现模糊不清的现象！
- 第二点需要注意的是，默认情况下。一条线只占用0.5px 。所以线条显得比较灰色，如果要解决这问题，则需要在设置的时候，给多给0.5px 即可！
