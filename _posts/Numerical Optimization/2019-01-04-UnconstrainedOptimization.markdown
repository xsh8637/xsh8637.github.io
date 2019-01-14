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
&emsp;&emsp;1. Line Search: 假设在某点x<sub>k</sub>，寻找方向p<sub>k</sub>和步长α使得f(x<sub>k</sub>+αp<sub>k</sub>)最小:<
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.10.png)
&emsp;&emsp;2. Trust Region: 对于函数f在x<sub>k</sub>点的近似解m<sub>k</sub>，必须保证m<sub>k</sub>为一个较好的近似，所以必须在x<sub>k</sub>附近找到这样这样的m<sub>k</sub>(即最优解的近似解，必须在最优解附近才是好的近似解).所以要找到一个候选step p，可以通过近似解决下面的问题:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.11.png)
&emsp;&emsp;&emsp;&emsp;信赖域如果过大，我们则缩小信赖域，信赖域定义满足||p||<sub>2</sub>≤Δ.2.11的式子写成二次方程的形式如下:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.12.png)
&emsp;&emsp;&emsp;&emsp;下图是信赖域的示意图(线搜索和信赖域的区别主要是在选择方向和距离的顺序上，先搜索先选择方向，信赖域先选择距离):
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.12b.png)


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
&emsp;&emsp;&emsp;&emsp;由上式推导可得:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.15b.png)
&emsp;&emsp;&emsp;&emsp;只要∇f<sub>k</sub>不为0，牛顿方向则是下降方向。同理，如果为0，则牛顿方向就不存在(无法定义)，因此需要改变p<sub>k</sub>的定义(暂时不讨论)。牛顿方向依赖于计算Hessian 矩阵∇f<sup>2</sup><sub>k</sub>，比较低效。<br>
&emsp;&emsp;3. 拟牛顿方向(Quasi-Newton Direction)<br>
&emsp;&emsp;&emsp;&emsp;拟牛顿方法提供了避免计算Hessian矩阵，并且收敛性也很好的方法。使用一个近似项B<sub>k</sub>来代替Hessian 矩阵∇f<sup>2</sup><sub>k</sub>的计算。改写∇f<sup>2</sup><sub>k</sub>p的定义(泰勒展开):
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.15c.png)
&emsp;&emsp;&emsp;&emsp;∇f(.)是连续的，最后的一个整数项大小为o(||p||)。令x=x<sub>k</sub> && p=x<sub>k-1</sub> - x<sub>k</sub>，则有
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.15d.png)
&emsp;&emsp;&emsp;&emsp;x<sub>k</sub>和x<sub>k+1</sub>在解x<sup>*</sup>附近，并且∇<sub>2</sub>f是正定的，因此忽略最后的极小项，有
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.16.png)
&emsp;&emsp;&emsp;&emsp;用割线方程B<sub>k+1</sub>s<sub>k</sub> = y<sub>k</sub>解释上式，其中s<sub>k+1</sub> = x<sub>k+1</sub> - x<sub>k</sub>, y<sub>k</sub> = ∇f<sub>k+1</sub> - ∇f<sub>k</sub>.
&emsp;&emsp;&emsp;&emsp;这时我们只要逐步求解B<sub>k+1</sub>，有两种方法:<br>
&emsp;&emsp;&emsp;&emsp;a. symmetric-rank-one(SR1)
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.18.png)
&emsp;&emsp;&emsp;&emsp;b. BFGS
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.19.png)
&emsp;&emsp;&emsp;&emsp;根据割线方程，有:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.20.png)
&emsp;&emsp;&emsp;&emsp;令H<sub>k</sub>=B<sub>k</sub><sup>-1</sup>，2.18和2.19变形得到下式:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.21.png)
&emsp;&emsp;&emsp;&emsp;求解p<sub>k</sub>，可以有p<sub>k</sub>=-H<sub>k</sub>∇f<sub>k</sub>.<br>
&emsp;&emsp;4. 非线性共轭梯度方向(nonlinear conjugate gradient methods)<br>
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.21a.png)
&emsp;&emsp;&emsp;&emsp;共轭梯度方法是用来求解线性方程Ax=b的一种方法，等价于求解凸二次方程
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.21b.png)
&emsp;&emsp;&emsp;&emsp;因此该方法比最速下降法还要高效；最速下降法和非线性共轭梯度法虽然收敛效率没有牛顿和拟牛顿法那么高，但是它们不需要存储矩阵。<br>


### &emsp;&emsp;C. 信任域(Trust Region)模型
&emsp;&emsp;如果B<sub>k</sub> = 0，则信赖域问题变成如下:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.21c.png)
&emsp;&emsp;求解p<sub>k</sub>，变成下式:
![](/images/NumericalOptimization_2019-01-04-UnconstrainedOptimization/2.21d.png)

### &emsp;&emsp;D. Scaling问题
&emsp;&emsp;1. 一个算法的表现好坏，其中一个很重要的问题就是scaling.一个poorly scaled问题是指函数f(x)在某个方向上的变化比其他方向的变化，带来更大的函数值改动.(例子: f(x) = 10<sup>9</sup>x<sub>1</sub> + x<sub>2</sub>.)<br>
&emsp;&emsp;2. 最速下降法就是poorly scaled算法, Newton法也会受到影响.因此scale invariance在算法中是很重要的，影响算法的收敛性。<br>
