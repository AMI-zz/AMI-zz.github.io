---
title: html标签和css基础
---
盒模型指css布局中html中的每个元素在浏览器中的解析都可以被看作一个盒子，拥有盒子一样的外形和平面空间。元素的盒子宽度：content+padding+border+margin 

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


### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/deployment.html)
