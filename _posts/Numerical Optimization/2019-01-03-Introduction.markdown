---
layout:     post
title:      "Numerical Optimization: Introduction"
subtitle:   "数值优化_序"
date:       2019-01-03 19:30:00
author:     "Thomas"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数值优化
    - Numerical Optimization
---

> “数值优化为解最优化问题提供一种迭代算法思路，通过迭代逐渐接近最优解。”


## 一、简介

&emsp;&emsp;示例<br>
&emsp;&emsp;&emsp;&emsp;1. 投资组合最优: 高回报，低风险<br>
&emsp;&emsp;&emsp;&emsp;2. 自然界最优: 物理系统最低能量态<br>
&emsp;&emsp;&emsp;&emsp;3. ...<br>
&emsp;&emsp;数值优化是通过迭代的方式解决最优化问题，是数学建模(modeling)的重要环节。<br>
&emsp;&emsp;Modeling需要确定优化目标、目标依赖的变量以及变量间的约束关系。<br>


## 二、数学描述(mathematical formulation)
&emsp;&emsp;数学描述，优化问题是满足变量约束的前提下最小化or最大化一个目标函数。<br>
&emsp;&emsp;Notation:
&emsp;&emsp;&emsp;&emsp;- x 是变量or参数(向量);
&emsp;&emsp;&emsp;&emsp;- y 是关于x的目标函数;
&emsp;&emsp;&emsp;&emsp;- ci 是x的限制条件。
![](/images/NumericalOptimization_2019-01-03-Introduction/1.1.png)


&emsp;&emsp;DDPG中使用一个神经网络来近似值函数，此值函数网络又称critic网络，它的输入是 action与observation [s,a]，输出是Q(s,a)；另外使用一个神经网络来近似策略函数，此policy网络又称actor网络，它的输入是observation s，输出是action a.<br>
![](/images/2018-12-03-DDPG/DDPG.jpeg)
【我还没完。。。】
