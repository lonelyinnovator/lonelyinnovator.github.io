---
title: 解决jupyter lab中暗色主题坐标轴看不清的问题
date: 2022-10-23 13:18:55
categories: jupyter-lab
tags: [python, jupyter-lab]
urlname: solve-dark-theme-for-jupyter-lab
---


## jupyter lab暗色模式
发现jupyter lab中，暗色模式下看不清图片的坐标轴
<img src="https://s1.imagehub.cc/images/2022/10/23/imageb49a5246d1c2a106.png" alt="imageb49a5246d1c2a106.png" border="0" />

这可不行捏，那么如何在暗色模式下解决该问题呢？
发现只要导个包就行啦：
```python
from jupyterthemes import jtplot
jtplot.style(theme='onedork')
```
这里是效果：
<img src="https://s1.imagehub.cc/images/2022/10/23/imagedd93ce36c47ae0a1.png" alt="imagedd93ce36c47ae0a1.png" border="0" />

特意在博客里记录一下，防止自己忘记捏=v=
