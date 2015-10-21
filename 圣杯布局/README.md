### 圣杯布局

左右两栏宽度。中间部分自适应。

先布局中间，再布局左，再布局右。

三个部分都设置为float:left和position:relative;

外层通过对container进行padding设置，布局好中间自适应的部分。<div>部分middle在前。

    .container {
        //经典布局，暂时还没悟到和单独使用margin的区别
        padding:0 220px 0 200px;
        overflow: hidden;
    }

    .middle {
        width: 100%;
        background: blue;
    }  

左侧先将位置调整到左边缘与middle对其，然后相对左移宽度的距离。

    .left {
        margin-left: -100%;
        left: -200px;
        width: 200px;
        background: red;	
    }

右侧先将位置调整到右边缘和middle右侧对其，然后相对右移宽度的距离。

    .right {
        margin-left: -220px;
        right: -220px;
        width: 220px;
        background: green;
    }
}

总而言之，该实现使用了margin为负值会压缩元素宽度，在文档流中将元素的边界向里收，文档流认的只是这个边界，不会管你实际的尺寸是多少。当margin的负值超过元素宽度时，相当于当前元素不占据空间，元素边界还在继续移动，那么因为空间不够而换行的元素，这时候会回到上一行，并且根据margin负值的增大继续移动位置。

某个元素虽然是写在了后面，但可以通过负边距让它在浏览器显示的时候是在前面的，通过这个特性，圣杯模型得以实现。

[参考资料：margin负值](http://www.cnblogs.com/2050/archive/2012/08/13/2636467.html)

如果使用flex布局，圣杯布局会简单很多：

将container设置为display:flex;

左侧和右侧宽度依次设置为200px和220px，将中间设置为flex:1。因为左右的宽度固定，所以flex占据了伸缩盒的剩余部分。(存在一个问题，左侧会比中间先加载)

所谓的双飞翼布局则更好理解：

通过在middle中间设置middle-inner,使左右部分到达middle的边缘之后不用在进行位置调整，因为middle的边缘就是父容器的边缘，中间的定位通过middle-inner实现
