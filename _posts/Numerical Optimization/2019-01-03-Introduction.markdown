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


## 二、数学描述
&emsp;&emsp;数学描述，优化问题是满足变量约束的前提下最小化or最大化一个目标函数。<br>
&emsp;&emsp;Notation:<br>
&emsp;&emsp;&emsp;&emsp;- <i>x</i> 是变量or参数(向量);<br>
&emsp;&emsp;&emsp;&emsp;- <i>f</i> 是关于x的目标函数;<br>
&emsp;&emsp;&emsp;&emsp;- <i>c<sub>i</sub></i> 是x的限制条件。<br>
![](/images/NumericalOptimization_2019-01-03-Introduction/1.1.png)<br>
&emsp;&emsp;考虑一个简单问题:<br>
![](/images/NumericalOptimization_2019-01-03-Introduction/1.2.png)<br>
&emsp;&emsp;上面问题的几何表示:<br>
![](/images/NumericalOptimization_2019-01-03-Introduction/1.2p.png)<br>
&emsp;&emsp;这个问题表示成1.1的形式:<br>
![](/images/NumericalOptimization_2019-01-03-Introduction/1.1a.png)<br>

#### &emsp;&emsp;问题分类<br>
&emsp;&emsp;根据目标函数或者约束条件的不同，最优化问题可以有如下分类:<br>
&emsp;&emsp;&emsp;&emsp;* 连续/离散化优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 约束/非约束优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 线性/非线性优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 全局/局部优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 随机/确定性优化问题<br>

#### &emsp;&emsp;凸优化<br>

【我还没完。。。】
