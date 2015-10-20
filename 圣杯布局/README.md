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

如果使用flex布局，圣杯布局会简单很多：

将container设置为display:flex;

左侧和右侧宽度依次设置为200px和220px，将中间设置为flex:1。因为左右的宽度固定，所以flex占据了伸缩盒的剩余部分。

所谓的双飞翼布局则更好理解：

通过在middle中间设置middle-inner,使左右部分到达middle的边缘之后不用在进行位置调整，因为middle的边缘就是父容器的边缘，中间的定位通过middle-inner实现
