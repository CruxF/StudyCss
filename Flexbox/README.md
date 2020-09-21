## 什么是flexbox布局？
flexbox的出现是为了解决逐渐复杂的web布局问题，因为这种布局方式很灵活。容器的子元素可以任意方向进行排列。 flex布局模型不同于块模型布局和内联模型布局，块和内联模型的布局计算依赖于块和内联的流方向，而flex布局依赖于flex directions。简单的说：flexbox是布局模块，而不是一个简单的属性，它包含父元素(flex container)和子元素(flex items)的属性。

## flexbox布局属性全解析
强大且灵活的flexbox布局，让广大的前端开发者省去了解决盒子浮动所带来的苦恼。在如今手机端开发成为主流时代的，这种布局尤为重要，下面我们一起看看flexbox布局中各种属性所发挥的作用。

### 1、display(flex container)属性
这个属性是在父元素中设置的，当父元素设置了该属性，那么默认其中的子元素横向布局，就和浮动布局一般，下面来看代码：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        width: 80px;
        margin-top: 10px;
        margin-right: 10px;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">row1</div>
      <div class="item2">row2</div>
      <div class="item3">row3</div>
    </div>
  </body>
</html>
```
点击我看[演示效果](https://cruxf.github.io/Flexbox-Advanced/demo1)哦。


### 2、flex-direction(flex container)属性
这个属性在父元素中定义，作用是改变子元素的布局方向，主要有以下几个属性值：
- row：这个是默认值，定义子元素从左向右布局；
- row-reverse：定义子元素从右向左布局；
- column：定义子元素顺序从上到下布局；
- column：定义子元素反序从上到下布局；

下面贴一部分代码：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
        flex-direction: column;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        width: 80px;
        margin-top: 10px;
        margin-right: 10px;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">row1</div>
      <div class="item2">row2</div>
      <div class="item3">row3</div>
    </div>
  </body>
</html>
```
更详细[戳我看效果](https://cruxf.github.io/Flexbox-Advanced/demo2)啊，具体实现请看demo中的**网页源代码**。


### 3、order(flex items)属性
这个属性是定义在子元素中，作用是改变子元素在布局流中的位置。在父元素定义了布局方式为flex时，各个子元素的默认order值为0，当子元素order值设置为负值时向前排序，设置为正值向后排序，设置为0时为正常排序，下面请看代码：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        width: 80px;
        margin-top: 10px;
        margin-right: 10px;
        text-align: center;
      }
      .item2 {
        order: 1;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">order1</div>
      <div class="item2">order2</div>
      <div class="item3">order3</div>
    </div>
  </body>
</html>
```
点击[这里看效果](https://cruxf.github.io/Flexbox-Advanced/demo3)哦。

### 4、flex-wrap(flex container)属性
这个属性定义在父元素中，它的作用是设置子元素在页面缩小时，到底是在一行显示还是换行显示，主要有以下几个属性值：
- nowrap：这个是默认值，定义子元素当页面缩小时，还是在一行显示；
- wrap：定义子元素当页面缩小时，换行顺序显示；
- wrap-reverse：定义子元素当页面缩小时，换行反序显示；

下面贴核心代码，默认源代码请到项目源地址或者网页上查看，不说第二次了
```
.boxThree {
    display: flex;
    display: -webkit-flex;
    flex-wrap: wrap-reverse;
 }
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo4)哦


### 5、flex-flow(flex container)属性
这个属性定义在父元素中，它是flex-direction和flex-wrap这两个属性的缩写版本，但是在这场景下，flex-direction的属性值只能为row或者row-reverse，下面列举3种组合：
- row wrap ：横向顺序布局，页面缩小时换行顺序显示；
- row wrap-reverse：横向顺序布局，页面缩小时换行反序显示；
- row-reverse wrap：横向反序布局，页面缩小时换行顺序显示。

还有几种组合方式，大家可以去尝试一下，在这里不全部举出，下面贴出某一段核心代码：
```
.boxTwo {
    display: flex;
    display: -webkit-flex;
    flex-flow: row-reverse wrap;
}
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo5)哦

### 6、justify-content(flex container)属性
这个属性定义在父元素中，它的作用是让子元素以怎样的方式横向布局显示，主要有下面几个属性值：
- flex-start：这个是默认值，让子元素横向布局，方向是从左往右；
- flex-end：让子元素横向布局，方向是从右往左；
- center：让子元素横向居中布局；
- space-between：让子元素横向布局，每个子元素平均分布在父元素；
- spack-around：让子元素横向布局，每个子元素平均分布在父元素，并且在两端会有空间。

下面贴出某一段核心代码：
```
.boxThree {
    display: flex;
    display: -webkit-flex;
    justify-content: center;
}
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo6)哦


### 7、align-content(flex container)属性
这个属性定义在父元素中，十分怪异的一个属性，它有以下几个使用的前提：
- 1、需要父元素有高度，并且不能高于几个子元素高度之和；
- 2、需要设置父元素中的子元素为纵向布局(column)；
- 3、需要设置父元素中的子元素能换行显示(wrap)。

属性值与justify-content类似，相比只是多了个stretch。下面贴出某段核心代码：
```
.boxSix {
    display: flex;
    display: -webkit-flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-content: stretch;
    height: 300px;
    width: 800px;
    border: 1px solid #ccc;
}
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo7)哦


### 8、align-items(flex container)属性
这个属性定义在父元素中，是一个十分常用的属性，它的作用是改变子元素纵向布局的方式，主要有以下几个属性值：
- flex-start：让子元素最上、最左布局；
- flex-end：让子元素最底、最左布局；
- center：让子元素垂直居中布局；
- baseline：让子元素根据里面的内容的基线对齐（不理解没关系，请看下方的demo）；
- stretch：这个是默认值，与flex-start值发挥的作用看上去一毛一样，实际上有什么区别我也不太懂。

下面贴出某段核心代码：
```
.boxFour {
    display: flex;
    display: -webkit-flex;
    align-items: baseline;
    height: 300px;
    width: 800px;
    border: 1px solid brown;
}
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo8)哦


### 9、align-sef(flex items)属性
这个属性定义在子元素中，它的作用是改变某个子元素在纵轴方向的布局方式，主要有以下几个属性值：
- auto：让某个子元素自动布局，很佛性，一般是跟着周围的子元素布局方式走；
- flex-start：让某个子元素贴着顶部方向布局；
- flex-end：让某个子元素贴着底部方向布局；
- center：让某个子元素垂直居中布局；
- baseline：让某个子元素根据内容基线来布局；
- strech：这个是默认值，和flex-start值发挥的作用看上去一毛一样。

下面贴出某段核心代码：
```
.item14 {
    height: 190px;
    font-size: 28px;
    align-self: baseline;
}
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo9)哦


### 10、flex-grow(flex-items)属性
这个属性定义在子元素中，是非常实用的一个属性，它的作用是让子元素以几倍宽度拉伸，属性值的类型为number，下面贴出全部代码：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>flex-grow</title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        margin-right: 10px;
        text-align: center;
        flex: 1;
      }
      .item1 {
        flex-grow: 2;
      }
      .item2 {
        flex-grow: 4;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">两倍宽度</div>
      <div class="item2">四倍宽度</div>
      <div class="item3">一倍宽度</div>
    </div>
  </body>
</html>
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo10)哦


### 11、flex-shrink(flex items)属性
这个属性定义在子元素中，它的作用就是让子元素在页面缩小时宽度如何变化，属性值为number，默认值是1。当值为2时，说明页面缩小时，该子元素将相对缩小两倍；当值为0时，页面缩小时，该子元素宽度不会发生改变。下面请看全部代码：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>flex-shrink</title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        width: 400px;
        margin-right: 10px;
        text-align: center;
      }
      .item2 {
        flex-shrink: 0;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">flex-shrink</div>
      <div class="item2">flex-shrink</div>
      <div class="item3">flex-shrink</div>
    </div>
  </body>
</html>
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo11)哦


### 12、flex-basis(flex items)属性
这个属性定义在子元素中，具体的作用我也不是很清楚，只是知道它的值只有两个，一个为auto，另一个为0，下面贴代码给大家来研究研究：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>flex-basis</title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        margin-right: 10px;
      }
      .item2 {
        flex-basis: 0;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">flex-shrink</div>
      <div class="item2">flex-shrink</div>
      <div class="item3">flex-shrink</div>
    </div>
  </body>
</html>
```
如果把类名为item2的内容换成别的，你们看看会出现什么情况？点击我[查看上述代码效果](https://cruxf.github.io/Flexbox-Advanced/demo12)哦


### 13、flex(flex items)属性
这个属性定义在子元素中，是flex-grow、flex-shrink、flex-basis这三个属性的缩写。默认值为“0 1 auto”，下面请看一段代码：
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>flex</title>
    <style>
      .box {
        display: flex;
        display: -webkit-flex;
      }
      .item1, .item2, .item3 {
        background: #FFA500;
        padding: 10px;
        height: 100px;
        margin-right: 10px;
        text-align: center;
        flex: 1;
      }
      .item2 {
        flex: 2 0 auto;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <div class="item1">flex</div>
      <div class="item2">flex-double</div>
      <div class="item3">flex</div>
    </div>
  </body>
</html>
```
点击我[查看效果](https://cruxf.github.io/Flexbox-Advanced/demo13)哦


## 尾声
终于把flexbox布局的那些玩意探究的差不多了，真的是累，花了近一整天的时间，不过收获却是巨大的，之前对flexbox布局还是迷迷糊糊的，经过这次的总结和探究，算是进一步深入理解了。对flexbox布局的完全掌握我认为还是得经常将它运用在项目之中，多踩踩兼容的坑，同时也能将它熟记于心。



