---
layout:     post
title:      "Numerical Optimization: Line Search Methods"
subtitle:   "数值优化_线搜索方法"
date:       2019-01-14 20:40:00
author:     "Thomas"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数值优化
    - Numerical Optimization
---

> “线搜索方法是求解最优化问题的一类非常重要的迭代算法。”


## 一、定义
&emsp;&emsp;线搜索方法迭代的过程是先选择一个迭代方向<i>p<sub>k</sub></i>，然后决定在这个方向上移动的距离α<sub>k</sub>. 如下式
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/3.1.png)
