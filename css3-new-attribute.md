#CSS3新增属性

##文本新增属性

- 文字阴影 
    
    `text-shadow: x1 y1 阴影范围1 阴影颜色1,x2 y2 阴影范围2 阴影颜色2;`

- 文字描边

   ` webkit-text-stroke:宽度 颜色;`
    
- 文字排列方式

   ` direction:ltr 从左到右 rtl从右到左;`
   
    一般要配合
	unicode-bidi:bidi-override;
	
- 超出显示省略号

```
	white-space:nowrap;
	
	overflow:hidden;
	
	text-overflow:ellipsis;
```
	
- 自定义字体

```
    @font-face{    
		font-family:;
		src:url()format();
			url()format();
			url()format();
		font-weight:normal;
		font-style: normal;

	}
```

##盒模型属性
- 阴影

    box-shadow:[inset] x y blur [spread] color，[inset] x y blur [spread] color;
	
	参数
	- inset：投影方式
		- inset：内投影
		- 不给：外投影

	- x、y：阴影偏移

	- blur：模糊半径

	- spread：扩展阴影半径。先扩展原有形状，再开始画阴影
	
	- color：阴影颜色
- 倒影

    -webkit-box-reflect:above|below|left|right;
    
	- direction  方向     above|below|left|right;
	
	- 距离
	
	- 渐变（可选）
- 自由缩放

	resize 自由缩放
	
	- Both 水平垂直都可以缩放
	
	- Horizontal 只有水平方向可以缩放
	
	- Vertical 只有垂直方向可以缩放
	
	注意：一定要配合overflow:auto 一起使用只有水平方向可以缩放

- 盒模型解析模式

	box-sizing 
	
	- Content-box  标准盒模型 width/height=border+padding+content
	- Border-box 怪异盒模型 width/height=content
	
##分栏布局(webkit)

- column-width 栏目宽度
- column-count 栏目列数
- column-gap   栏目距离
- column-rule  栏目间隔线 

##设置圆角
- 圆角四个角的设置方式：

	box-radius:四个角半径;
	
	box-radius:1、3角半径 2、4角半径;
	
	box-radius:角半径1 角半径2、4 角半径3;
	
	box-radius:角半径1 角半径2 角半径3 角半径4;

- 椭圆圆角设置方式
	
	box-radius:X轴半径1 X轴半径2 X轴半径3 X轴半径4/Y轴半径1 Y轴半径2 Y轴半径3 Y轴半径4 ; 
	
##设置边框背景
- 边框宽

    border-(left)-width 设置边框宽度 可对边框背景进行缩放或者拉升

- 设置边框背景图片

	border-image:url(border.png) 上下裁切高度 左右裁切高度 横向 纵向  ;
	
	横向 纵向可设置：stretch(拉升) round(平铺) repeat(重复) round和repeat一样
	
##线性渐变
只能用在背景上

`background-image:-webkit-linear-gradient(left top red 30%, blue 60%);`
	
`background-image:-webkit-linear-gradient(30deg,red,blue)`
	
`background-image:-webkit-repeating-linear-gradient(30deg,red,blue)`

IE：

`filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffff',endColorstr='#ff0000',GradientType='1');`
	
GradientType='0':上下渐变

##径向渐变
- background:-webkit-radial-gradient(left top,red,blue)

- 起点:可以是关键字(left,top,right,
	bottom)或结合使用，具体数值可以是数值或者百分比(坐标xy)

- 形状:ellipse\circle

- 大小:具体数值或百分比，也可以是关键字(最近端、最近角、最远端、最远角，
	
	包含或覆盖(closest-side、closest-corner、farthest-side、farthest-corner、contain or cover))。火狐只支持关键字

##图片背景
可以设置多个背景 

`background:url(img/1.png)no-repeat 0 0, url(img/2.png)`
先写的盖在上面

- background-size:100px 200px; 背景大小
- background-size:cover 覆盖 等比例铺开直到一个方向铺满 
	另外一个方向有可能超出元素
- background-size:contain 包含 等比例放铺在元素内，直到一个方向铺满

- background-origin ： border | padding | content 
	- border-box： 从border区域开始显示背景。 
	- padding-box： 从padding区域开始显示背景。 
	- content-box： 从content区域开始显示背景。

- background-clip
	- border-box： 从border区域向外裁剪背景。 
	- padding-box： 从padding区域向外裁剪背景。 
	- content-box： 从content区域向外裁剪背景。 
	- text: 只在文字区域内有背景(只在wenkit内核下实现了)
	- no-clip-box： 从border区域向外裁剪背景。


##遮罩(webkit)
- mask-image
- mask-position
- mask-repeat

##动画过度
- transition-property  要运动的样式  （all || [attr] || none）
- transition-duration 运动时间
- transition-delay 延迟时间
- transition-timing-function 运动形式 
	- ease：（逐渐变慢）默认值
	- linear：（匀速）
	- ease-in：(加速)
	- ease-out：（减速）
	- ease-in-out：（先加速后减速）
	- cubic-bezier 贝塞尔曲线（ x1, y1, x2, y2 ） 

- transition事件

	- Webkit内核：
	
		`obj.addEventListener('webkitTransitionEnd',function(){},false);`

	- firefox:
	
		`obj.addEventListener('transitionend',function(){},false);`

- transition事件的执行顺序

    transition的执行顺序在页面渲染之后

##2D变换
- transform
    - rotate()  旋转函数 取值度数
		- deg  度数
		- Transform-origin 旋转的基点
	- kew() 倾斜函数 取值度数 
	- skewX()
	- skewY()
	- scale() 缩放函数 取值 正数、负数和小数
	- scaleX()
	- scaleY()
	- translate() 位移函数
	- translateX()
	- translateY()

- transform 执行顺序问题 — 后写先执行
	
	比如:
	
	1.-webkit-transform:translateX(100px) scale(0.5);
	是先计算缩小0.5，再计算移动100px,所以元素向右移动了100px并且缩小0.5倍

	2.-webkit-transform: scale(0.5) translateX(100px);
	是先计算移动100px，再计算缩小0.5,所以元素向右移动了50px并且缩小0.5倍

- transform : matrix(a,b,c,d,e,f)矩阵函数

##3D变换
- transform-style : preserve-3d 建立3D空间
	
- perspective 景深

- Perspective-origin 景深基点

- Transform 新增函数
	- rotateX()
	- rotateY()
	- rotateZ()
	- translateZ()
	- scaleZ()
