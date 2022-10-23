---
title: 为typora更换主题并更改样式
date: 2022-10-22 10:16:42
categories: typora
tags: [typora, css]
urlname: change-typora-theme
---

## 获取主题

打开typora[获取主题](https://theme.typora.io/)网页，选择`Light Monokai`主题下载
然后将下载得到的css文件复制到typora的主题文件夹中，如下图：

<div>
    <img src="https://s1.imagehub.cc/images/2022/10/22/image.png" alt="get-typora-theme.png" border="0" />
</div>

## 更改样式
在typora主题文件夹下创建`light-monokai.user.css`文件，作为用户自定义的样式，可以覆盖原有的主题的样式。
想要个好看点的深色主题，更改如下：

#### 设置悬浮在可点击的标签上的背景颜色，以及选中文本时的背景颜色

暗色模式下，悬浮的背景色太亮了，想要改暗一点

```css
:root{
    --item-hover-bg-color: #555;
    --select-text-bg-color: #555;
}
```

<img src="https://s1.imagehub.cc/images/2022/10/22/image8861b27ac62cce9f.png" alt="image8861b27ac62cce9f.png" border="0"/>

<br>

<img src="https://s1.imagehub.cc/images/2022/10/22/image54d27121a6887f15.png" alt="image54d27121a6887f15.png" border="0" style="width: 80%" />

#### 设置a标签的字体大小

light-monokai的a标签字体大小有一定的问题，更改成继承，不设置大小

```css
a{
    font-size: inherit;
}
```

#### 设置h1和h2标签的下划线

本来github主题有下划线，看起来不错，改一下border的颜色就有了

```css
h1,
h2{
    border-bottom: 1px solid #333;
}
```

<img src="https://s1.imagehub.cc/images/2022/10/22/image565d755b8b035396.png" alt="image565d755b8b035396.png" border="0" style="width: 50%" />

#### 更改代码和代码块的字体

还是习惯用consolas捏=v=

```css
code,
pre{
    font-family: consolas;
}
```

#### 更改文档内边距

文档看着感觉太窄了，内边距改小了些

```css
#write {
    max-width: 100%;
	padding: 30px 180px;
}
```

#### 减小无序列表和有序列表的缩进

```css
ul, ol{
    margin-left: 10px;
}
```

#### 更改文本的行间距

```css
.md-math-block,
.md-rawblock,
h1,
h2,
h3,
h4,
h5,
h6,
p {
    margin: 1rem 0;
}
```

#### 更改侧边栏的背景颜色

```css
#ty-sidebar-footer{
    border-top-color: #282927;
}
#ty-sidebar-footer{
    border-top-color: #282927;
}
```

#### 更改公式块的背景颜色

公式块的背景色是白色的，字也是白的，所以背景要改成黑的，可以用开发者工具查看选择器

```css
div.md-mathblock-panel.md-rawblock-panel > div.md-rawblock-control.md-rawblock-before,
div.md-mathblock-panel.md-rawblock-panel > div.md-rawblock-control.md-rawblock-input.md-mathblock-input,
div.md-mathblock-panel.md-rawblock-panel > div.md-rawblock-control.md-rawblock-after{
    background-color: #000;
    font-family: consolas;
}
```



### 更改样式效果

<img src="https://s1.imagehub.cc/images/2022/10/22/imagee4ab02a27e9152b1.png" alt="imagee4ab02a27e9152b1.png" border="0" />



                