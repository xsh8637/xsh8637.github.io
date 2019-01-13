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
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.1.png)
&emsp;&emsp;举个例子:<br>
&emsp;&emsp;&emsp;&emsp;假设有如下目标函数:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.1a.png)
&emsp;&emsp;&emsp;&emsp;φ(t<sub>j</sub>;x)如果要尽可能的接近观察值y<sub>j</sub>，定义它们之间的差:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.2.png)
&emsp;&emsp;&emsp;&emsp;其实我们要解决的是如下的问题:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.3.png)
&emsp;&emsp;&emsp;&emsp;局部最优解就是存在一个局部的x<sup>*</sup>使得它周围的x都有<i>f(x<sup>*</sup>) < f(x)</i>.<br>

## 二、局部最优解相关定理
&emsp;&emsp;1. 泰勒展开式:<br>
&emsp;&emsp;&emsp;&emsp;一阶泰勒展开: f(x)≈f(x0)+∇f(x0)T(x−x0)<br>
&emsp;&emsp;&emsp;&emsp;二阶泰勒展开: f(x)≈f(x0)+∇f(x0)T(x−x0)+12(x−x0)T∇2f(x0)(x−x0)<br>
&emsp;&emsp;2. 局部最小值的一阶必要条件，如果x<sup>*</sup>为局部最优解并且函数f一阶可导，则在x<sup>*</sup>的邻域内∇f(x<sup>*</sup>)=0<br>
&emsp;&emsp;3. 局部最优解的二阶必要条件，如果x<sup>*</sup>为局部最优解并且一阶和二阶可导，则∇f(x<sup>*</sup>)=0 并且∇2f(x)正定<br>
&emsp;&emsp;&emsp;&emsp;证明: 定理2,3可以用反证法(略).<br>
&emsp;&emsp;4. 局部最优的二阶充分条件：如果函数f在x<sup>*</sup>处满足∇f(x<sup>*</sup>)=0并且∇2f(x)正定，则x<sup>*</sup>为局部最优解.<br>
&emsp;&emsp;5. 如果函数f为凸函数，则f的任何局部最优解都为全局最优解.<br>
&emsp;&emsp;说明: 非平滑问题. 此问题不在讨论范围内，在此一般讨论二阶导数存在且连续的问题，对于非平滑甚至不连续的问题，一般会采用次梯度或者广义导数进行求解.<br>

## 三、优化算法
### &emsp;&emsp;A. 两种策略: 线搜索(Line Search)和信任域(Trust Region)
&emsp;&emsp;1. Line Search: 假设在某点x<sub>k</sub>，寻找方向p<sub>k</sub>和步长α使得f(x<sub>k</sub>+αp<sub>k</sub>)最小:<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.10.png)
&emsp;&emsp;2. Trust Region: 对于函数f在x<sub>k</sub>点的近似解m<sub>k</sub>，必须保证m<sub>k</sub>为一个较好的近似，所以必须在x<sub>k</sub>附近找到这样这样的m<sub>k</sub>.???(暂时还没看明白，待整理TODO)<br>

### &emsp;&emsp;B. Line Search中的搜索方向选择
&emsp;&emsp;1. 最速下降的方向，负梯度方向是最明显的选择，−∇f<sub>k</sub>。<br>
&emsp;&emsp;&emsp;&emsp;search方向<i>p</i>，步长α，因此进行二阶泰勒展开
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.12a.png)
&emsp;&emsp;&emsp;&emsp;由于∇<sup>2</sup>f<sub>k</sub>满足正定，因此等价于求解下面的问题
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.13.png)
&emsp;&emsp;&emsp;&emsp;至于为什么为负梯度方向，如下面推导
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.13a.png)
&emsp;&emsp;2. 牛顿方向(Newton Direction)<br>
&emsp;&emsp;&emsp;&emsp;最速下降方向来自于一阶泰勒展开项，而牛顿方向就是来自于二阶泰勒展开项
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.14.png)
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.15.png)
&emsp;&emsp;&emsp;&emsp;上述的结论如何推导出来的?
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.15a.png)
&emsp;&emsp;3. 拟牛顿方向(Quasi-Newton Direction)<br>
