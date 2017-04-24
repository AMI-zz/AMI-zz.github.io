---
title: html标签和css基础
---
盒模型指css布局中html中的每个元素在浏览器中的解析都可以被看作一个盒子，拥有盒子一样的外形和平面空间。元素的盒子宽度：content+padding+border+margin 
![01-hezhi](../img/01-hezhi.png)
# 一、盒子模型
## 1.1内边距 padding
内边距： 元素内容和边框之间添加空白区域。padding扩大元素宽度

语法1：
padding-top | padding-left | padding-bottom | padding-right :  length;

属性	说明	值
padding-top	设置顶部的内边距	长度值或百分数
padding-right	设置右边的内边距	长度值或百分数
padding-bottom	设置底部的内边距	长度值或百分数
padding-left	设置左边的内边距	长度值或百分数
padding	简写属性，在一条声明中设置所有的内边距	1~4个长度值或百分数

如果使用百分数值制定内边距，百分数值是相对于其父元素的 width 计算的。

简写语法2
padding: 20px; 		     // 上 下 左 右 都是20px
padding: 20px 30px;       // 上下 20px，左右30px
padding: 20px 30px 40px;   // 上 20px， 左右 30px， 下 40px
padding: 20px 30px 40px  50px;  // 按照上，右，下，左的顺序设置

## 1.2外边距
外边距是元素边框和页面上围绕在它周围的所有东西之间的空白区域。
语法：margin-top | margin-right | margin-bottom | margin-left: length; 


属性	说明	值
margin-top	设置顶部的外边距	长度值或百分数
margin-right	设置右边的外边距	长度值或百分数
margin-bottom	设置底部的外边距	长度值或百分数
margin-left	设置左边的外边距	长度值或百分数
margin	简写属性，在一条声明中设置所有的外边距	1~4个长度值或百分数

margin的几种不同写法：
margin:10px 20px 10px 20px;     //上、右、下、左四个方位外边距的值
margin:10px 20px;       		 //上下、左右的外边距
margin:10px 20px 10px;       //上外边距，左右外边距，下外边距
margin:10px;                 //四个方向的外边距都10px
margin:20px auto;        // 上下的外边距为20px，左右的外边距自动适应居中
1.2.1margin注意事项:
竖向margin，同级之间以最大的值为准；
竖向margin，父子之间，如果是块属性标签或没有边框，则子级的竖向margin会传递给父级标签；
横向margin，同级是加法；
## 1.3处理溢出的内容
超出容器的内容需要出现滑动条或隐藏。
语法：
overflow：visible | hidden | auto | scroll
visible：显示超出内容，不剪切内容也不添加滚动条,默认属性 
hidden：超出内容隐藏
auto:，如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。 
scroll：总是显示滚动条
还可针对x轴和y轴设置
overflow-x：visible | hidden | auto | scroll 
overflow-y：visible | hidden | auto | scroll

## 1.4设置元素的盒类型
display改变元素在页面上的显示方式
值	说明
inline	元素会被显示成行内元素
block	此元素将显示成块级元素
inline-block	元素会被显示成行内的块级元素
none	元素既不显示，也不占据文档空间

1.4.1块级元素
块级元素(block element)
div -最常用的块级元素
h1~h6 - 标题
p - 段落
ul – 无排序列表
ol - 排序表单
dl - 和dt dd搭配使用的块级元素
form - 交互表单
块级元素特点
独占一行，对宽高的属性值生效；如果不给宽度，块级元素就默认为浏览器的宽度，即就是100%宽；

display：block   创建块级元素。

1.4.2行内元素
行内元素(inline element)
a - 锚点
span - 常用内联容器，定义文本内区块
em - 强调
label - 表格标签
strong - 粗体强调
textarea - 多行文本输入框
行内元素特点
可以多个标签存在一行，对宽高属性值不生效，完全靠内容撑开宽高！上下margin无效，上下padding无效。
display：inline   创建一个行内元素
1.4.3行内块级元素
img - 图片
input - 输入框
行内块级标签
不仅可以对宽高属性值生效，还可以多个标签存在一行显示。

display：inline-block    创建行内块级标签。


1.4.4隐藏元素
display：none   元素在页面中不显示，也不占据任何空间

visibility: hidden; 隐藏，保留标签的位置

## 1.5浮动
网页布局的方法： float(浮动布局)，postion(定位布局)，响应式布局(CSS3),在桌面端制作网页最常见的是float布局。
语法：
float: none | left | right
none : 对象不浮动；
left：左浮动；
right：右浮动；
1.5.1清除浮动的方法
overflow：hidden
如果一个父标签内有float的子元素，给父元素设置overflow：hidden属性，则可以清除子元素的浮动。

示例：

``` bash
<div class=“out”>
	<div class=“div1”></div>
	<div class=“div2”></div>
</div>

```

如果.div1和.div2都有浮动，那么给.out设置overflow:hidden; ,
即可清除 .div1和.div2的浮动

clear：none | left | right | both
none：允许浮动元素出现在两侧
left： 左侧不允许有浮动元素
right：右侧不允许有浮动元素
both： 不允许有浮动
例子：

``` bash
<div class=“clear”>&nbsp;</div>
.clear{clear:both;}

```

使用情况：由于元素的float，为了不影响下面元素的显示。通常在这个浮动元素的后面加上<div class=“clear”>&nbsp;</div>来消除对后面元素显示的影响。

1.5.2 float 对行内属性标签和块属性标签的影响
不管之前块标签还是行标签，加了浮动之后具备共同的特点
1.可以设置宽高，和margin和padding(上下)
2.在一行显示
3.内容撑开宽高
4.默认不占父级宽高

# 二、定位
position改变元素的默认位置

position:  absolute  |   relative   |  static  |  fixed  |  inherit 
absolute:绝对定位
relative:相对定位
static:该值为position的默认值
fixed:可定位相对于浏览器窗口的指定坐标
## 2.1相对定位
position: relative;
元素相对于其原有的位置进行定位，保留原有的位置，不脱离文档流
设置z-index: -1; 可以改变图层的显示顺序
				
## 2.2绝对定位	

position: absolute; 

1、绝对定位要与相对定位配合使用，若子元素为绝对定位，则父元素应设置为相对定位。

2、给盒子设置了绝对定位，该盒子不占位置（脱离文档流）

3、给行内元素设置绝对定位后，该元素转化为了行内块元素

4、若父元素没有设置相对定位，则按层级往上找父元素的父元素是否有相对定位；若都没有，则以body为基准

## 2.3fixed 固定定位

position: fixed;

1、固定定位不占位置（脱离文档流）

2、将行内元素转化为行内块元素


# 三、透明度
### 3.1  opacity属性定义元素的不透明度
语法：opacity: number(0-1之间的数值)
opacity的值为1的元素是完全不透明的反之，值为0的是完全透明的。
opacity: 0.8;
### 3.2  IE的半透明滤镜
语法：filter:alpha(opacity=number); 
number的取值为100-0之间的数值
因为ie不支持opacity，只支持自己的滤镜fiter:alpha(opacity=50);