
### line

##### lineCap
 butt(default)
 round
 square

 lineCap.html

##### lineJoin
 miter(default)
 bevel
 round

 star.html //五角星 的尖角 效果


##### miterLimit 
在 lineJoin 为miter时生效 

#### 图形变换

translate(x, y)

rotate(deg)

scale(sx, sy) //具有副作用，会影响其他属性

#### 变换矩阵
【a c e】  a d scale
【b d f】  b c skew
【0 0 1】  e f translate
 a 水平缩放（1）
 b 水平倾斜（0）
 c 垂直倾斜（0）
 d 垂直缩放（1）
 e 水平位移（0）
 f 垂直位移（0）
 ##### api
 ##### transform(a, b, c, d, e, f)
 ##### setTransform(a,b,c,d,e,f) //清除之前的transform

// 状态的保存    
context.save()
// 。。。操作画布
// 状态的恢复
context.restore()

##### fillStyle

##### 线性渐变
step1: var grd = context.createLinearGradient(xstart, ystart, xend, yend)

// stop 浮点数，颜色的位置（0.0 ~ 1.0）
// addColorStop可以添加多个
step2: grd.addColorStop(stop, color)

context.fillStyle = grd
context.fillRect(...)

##### 经向渐变
step1: var grd = context.createRadialGradient(x0, y0, r0, x1, y1, r1)
// x0 y0, r0 第一个圆的圆点坐标点和半径
// x1 y1, r1 第二个圆的圆点坐标点和半径

// stop 浮点数，颜色的位置（0.0 ~ 1.0）
// addColorStop可以添加多个
step2: grd.addColorStop(stop, color)

##### createPattern 图片填充/ canvas / video填充
context.fillStyle = createPattern([img | video | canvas], repeat-style)

repeat-style: no-repeat / repeat-x /repeat-y /repeat


##### 圆弧
context.arc(
    centerx, centery
    radius,
    stratDeg, endDeg,
    drectation
)
原型坐标
圆弧半径
起始角度，结束角度
绘制方向（是否是顺时针，默认是）

##### 圆弧方法2
moveTo(x0, y0)
arcTo (x1, y1, x2, y2, radius) 两个点的坐标和半径
三个点形成的两条线就是辅助线
起始点-控制点-结束点

##### 贝塞尔曲线
**二次曲线**
起始点-控制点-结束点
moveTo(x0, y0)
quadraticCurveTo(x1, y1, x2, y2)

##### 三次贝塞尔曲线
起始点-控制点-控制点-结束点
moveTo(x0, y0)
bezierCurveTo(x1, y1, x2, y2, x3, y3)

##### 文字渲染
context.font = 'font-size font-style font-weight...'
// 文本对齐
context.textAlign = 'left' | 'center' | 'right'
context.baseLine = 'top' | 'middle' | 'bottom'
// 文本度量
context.measureText(string).width

context.fillText(text, x, y, [maxlen])
maxlen:最长宽度
context.storkeText(text, x, y, [maxlen])