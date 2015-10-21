### margin折叠

  [参考资料](http://developer.51cto.com/art/201008/219288.htm)

  Collapsing margin，指的是毗邻的两个或多个外边距 (margin) 会合并成一个外边距，即外边距折叠。其中所说的 margin 毗邻，可以归结为以下两点：

1. 这两个或多个外边距没有被非空内容、padding、border或clear分隔开。

2. 这些margin都处于普通流(in-flow，非浮动元素，非定位元素)中。

具体规则：

1. 两个或多个毗邻的普通流中的块元素垂直方向上的margin会折叠
  
  A. 两个或多个

  B. 毗邻

  一个元素margin-top会和它普通流中的第一个子元素(非浮动元素等)的margin-top相邻；

  只有在一个元素的height是”auto”的情况下，它的margin-bottom才会和它普通流中的最后一个子元素(非浮动元素等)的margin-bottom相邻。

  C. 垂直方向

  D. 折叠后margin的计算  

  都是正数： 取其中margin较大的。

  有正由负： 先取出负margin中绝对值最大的，然后，和正marin值最大的magin，相加。

  都是负值： 取的是其中绝对值较大的，然后，从0位置，负向位移。

2. 浮动元素/inline-block的元素/绝对定位元素的margin不会和垂直方向上的其他元素的margin折叠

3. 创建了块级格式化内容的元素，不和它的子元素发生margin折叠（浮动元素，绝对定位元素，以及 overflow值不是’visible’的元素）

4. 元素自身的margin-bottom和margin-top相邻时也会折叠

