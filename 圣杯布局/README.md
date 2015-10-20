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
