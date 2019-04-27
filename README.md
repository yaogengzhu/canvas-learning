# canvas 使用文档
## canvas的起步
- 如何在canvas 上使用绘图第一个vans图呢？ 
    - 第一步： 需要获取canvas `var canvas = document.querySelect('canvas')` 
    - 第二步： 需要创建画布 `var ctx = canvas.getContext('2d')`此方式也称为获取上下文
    - 第三步： 绘制画图的起点 `ctx.moveTo(10,20)` 也可以称为移动画笔吧 
    - 第四步： 绘制路径`ctx.lineTo(100,20)`
    - 第五步： 填充路径（也叫描边） `ctx.stroke()`
**已经初步完成了canvas的绘制了**
## canvas绘图注意事项
- 首先需要注意的是  `canvas`只有width和height两个属性。canvas默认的宽高是300X150。 如果需要设置新的宽高，这需要在行内写出样式如： `<canvas widht=400 height=300  id="canvas"></canvas>` 这样设置canvas的宽高不会导致canvas的图像变形。如果使用style设置宽高，则可能出现模糊不清的现象！
- 第二点需要注意的是，默认情况下。一条线只占用0.5px 。所以线条显得比较灰色，如果要解决这问题，则需要在设置的时候，给多给0.5px 即可！

## canvas 绘制图片 
### 基本步骤如下：
- 画布假设已经创建好了  
- 第一步：创建一个img元素 ！`var img = new Image()`
- 第二步：由于图片是异步加载，需要先加载之后在操作！ `img.onload = function() { // 需要执行的代码～ }`
- 第三步：设置图片的src属性 `img.src ='图片路径'`

**绘制图片在`img.onload`代码中去执行** `src.drawImage(imm,20,20,200,200)` 可以传入五个参数。
    - 参数1 。创建的图片元素 
    - 参数2 。开始的x轴坐标；
    - 参数3 。 开始的y轴坐标；
    - 参数4 。 设置图片的宽度；
    - 参数5 。 设置图片的高度；

### globalCompositeOperation 详解 (拥有11个属性)
**globalCompositeOperation**即是canvas中的合成操作  
#### source-over 表示绘制的图形将在画在现有画布之上 
#### desitination-over 这个操作与source-over 相反，绘制目标源之上。
#### source-atop 这个操作会将源绘制在目标之上，但是在重叠区域两者都是不透明的，绘制在其他的目标位置是不透明的，但是源是透明的。
#### destination-atop 这个操作与source-atop相反，目标绘制在源之上
####  source-in 在源于目标重叠的区域只绘制源，而不重叠的部分编程透明的。
#### destination-in 这个操作与source-in相反，在源于目标重叠的区域保留目标。而不重叠的部分都变成透明的。
####  source-out 在与目标不重叠的区域上绘制源，其他部分都变成透明的。
#### destination-out 在与源不重叠的区域上保留目标。其他部分都变成透明的。
#### lighter 这个值与顺序无关，如果源与目标重叠，就将两者的颜色值想家。得到的颜色值的最大取值为255，结果就为白色。
#### copy 这个值与顺序无关，只绘制源，覆盖掉目标。
#### xor 这个值与顺序无关，只绘制出不重叠的源与目标区域。所有重叠的部分都变成透明的
