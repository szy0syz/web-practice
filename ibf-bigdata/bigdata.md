# 北风网-数据分析师页面练习

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