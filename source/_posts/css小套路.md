---
title: css实用小套路
date: 2017-11-06 23:05:21
tags: css
---
## 消除默认样式
### 1. 清除内外边框
很多元素会自带样式, 通常有margin和padding, 为了更好的布局, 可以把它们的内边框和外边框都清除, 每一个元素再相应的根据情况来设置内外边框.

    * {
        margin: 0;
        padding: 0;
    }
### 2. 清除a标签的样式
a标签自带了字体颜色, 和下划线, 如果要清除a标签的默认样式让下划线不再出现, 不仅仅要消除默认状态的下划线, hover状态的样式也要设置哦

    a {
        color: #FFF;
        text-decoration: none;
    }
    a:hover {
        text-decoration: none;
    }
### 3. 清除列表标签的样式:
无序列表和有序列表除了自带了margin和padding属性之外, 还自带了列表前面的小星标, 通过设置 list-style:none 来消除它

    ol, ul {
        list-style:none;
    }
## 清除浮动
以下是一个建议的清除浮动方法: 在浮动元素的父元素加上这个类, 利用了 :after伪类, 来清除浮动, 避免使用多余的标签.

    .clearfix:after{
        content='';
        display=block;
        clear:both;
    }
## 关于行内元素的宽和高设定
行内元素的宽和高是无法通过 height 和 width 属性来设置的, 除非将其变成一个块级元素.
好的做法是使用 padding 来将一个行内元素扩展到所需的高度和宽度.
