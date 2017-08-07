# 北风网-数据分析师页面练习

## 前言

> 话说最近帮媳妇找cda(数据分析师)的教程，找到了北风网，然后顺手做一下联系。话说level1和level2的课程中Excel、XMind、Visio、Tableau、ECharts、SPSS、SQL我都玩过，只是Python和一些写作技巧没玩过，是不是我也考一个玩玩。话说，一个cda竟然要还要玩到各种编程语言，这个想要深入真有些难度。

## 一、dom搭建

### topper 顶栏

- topper容器里包含两个div，分别是欢迎语和整站导航栏。
  - 欢迎语就是：您好,欢迎来到北风网!
  - 整站导航：社区 帮助 登录 注册 购物车
  - 购物车单独写样式

- topper的position为fixed，相对固定定位，意思就是永远定位在当前屏幕的最顶上。

- topper里的所有样式应该写在全局样式表里，因为可能不止一个页面在用。

来整一个emmet玩玩：

- `div.topper>div.w1200.clearfix>p.welworld+div.othlink`
  1. `.`表示类，后面跟类名，如果有多个类就连着写，但前面还得加`.` 
  2. `>`表示子元素，后面的所有都是前者的子元素
  3. `+`表示兄弟元素，后面跟元素标签等

```html
<div class="topper">
    <div class="w1200 clearfix">
        <p class="welworld fl"></p>
        <div class="othlink fr"></div>
    </div>
</div>
```

- `a[target=_blank href=#].none`
  - `[]`表示声明属性，多个属性用空白符连接

```html
<a href="#" target="_blank" class="none"></a>
```

- topper总结：
  - topper的dom结构就是div里各包含<p>和<div>，其中div里有又ul/li/a标签组成；
  - topper主样式，position:fixed，对象显示屏幕来定位；z-index:9999 因为必须保证不能被覆盖，显示在最上方；
  - 在设置li的上级div时，虽然已经设置了向右浮动，但因为a标签又在li标签中，所有需要再对所有a标签设置display: inline-block;让所有a标签设置在一行的块状元素；

> topper写完~