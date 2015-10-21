### 多列等高

    <div class='container'>
        <div class='left'></div>
        <div class='middle'></div>
        <div class='right'></div>
    </div>

利用的知识：

1. background包括padding部分

2. container被内部元素撑开，高度为内部元素盒子模型的高度

3. 用padding将高度补充到最高的同时，保证盒子模型的高度不变

4. 使用margin负值来减小边界位置

        .left
        .right
        .middle {
            padding-bottom: 2000px;
            margin-bottom: -2000px;
        }

