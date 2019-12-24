
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