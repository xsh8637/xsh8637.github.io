---
layout:     post
title:      "Numerical Optimization: Fundamentals of Unconstrained Optimization"
subtitle:   "数值优化_无约束最优化问题"
date:       2019-01-04 21:10:00
author:     "Thomas"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数值优化
    - Numerical Optimization
---

> “无约束最优化问题，只需要最小化目标函数而无变量间的约束。”


## 一、数学表达
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.1.png)<br>
&emsp;&emsp;举个例子:<br>
&emsp;&emsp;&emsp;&emsp;假设有如下目标函数:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.1a.png)<br>
&emsp;&emsp;&emsp;&emsp;φ(t<sub>j</sub>;x)如果要尽可能的接近观察值y<sub>j</sub>，定义它们之间的差:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.2.png)<br>
&emsp;&emsp;&emsp;&emsp;其实我们要解决的是如下的问题:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.3.png)<br>
&emsp;&emsp;&emsp;&emsp;局部最优解就是存在一个局部的x<sup>*</sup>是的它周围的x都有<i>f(x<sup>*</sup>) < f(x)</i>.<br>

