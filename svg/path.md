# PATH 指令

使用path标签时，就像用指令的方式来控制一只画笔，比如：移动画笔到某一坐标位置，画一条线，画一条曲线，完事了抬起画笔，OVER！

 

path支持的指令有：

 

M = moveto(M X,Y) ：将画笔移动到指定的坐标位置
L = lineto(L X,Y) ：画直线到指定的坐标位置
H = horizontal lineto(H X)：画水平线到指定的X坐标位置
V = vertical lineto(V Y)：画垂直线到指定的Y坐标位置
C = curveto(C X1,Y1,X2,Y2,ENDX,ENDY)：三次贝赛曲线
S = smooth curveto(S X2,Y2,ENDX,ENDY)
Q = quadratic Belzier curve(Q X,Y,ENDX,ENDY)：二次贝赛曲线
T = smooth quadratic Belzier curveto(T ENDX,ENDY)：映射
A = elliptical Arc(A RX,RY,XROTATION,FLAG1,FLAG2,X,Y)：弧线
Z = closepath()：关闭路径

 

其中蓝色的指令是我常用的，绿色的目前为止还没有用到

 

一、说明：

 

坐标轴为以(0,0)为中心，X轴水平向右，Y轴水平向下。
所有指令大小写均可。大写绝对定位，参照全局坐标系；小写相对定位，参照父容器坐标系
指令和数据间的空格可以省略
同一指令出现多次可以只用一个

 

二、指令

 

1、L H V指令

 

M　起点X，起点Y　L（直线）终点X，终点Y　H（水平线）终点X　V（垂直线）终点Y
如：M 10,20 L 80,50 M 10,20 V 50 M 10,20 H 90

 



 

 

2、A指令

 

允许不闭合。可以想像成是椭圆的某一段，共七个参数：

A RX,RY,XROTATION,FLAG1,FLAG2,X,Y



RX,RY指所在椭圆的半轴大小
XROTATION指椭圆的X轴与水平方向顺时针方向夹角，可以想像成一个水平的椭圆绕中心点顺时针旋转XROTATION的角度。
FLAG1只有两个值，1表示大角度弧线，0为小角度弧线。
FLAG2只有两个值，确定从起点至终点的方向，1为顺时针，0为逆时针
X,Y为终点坐标


如：m 200,250 a 150,30 0 1 0 0,70