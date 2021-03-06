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

## 三、问题分类
&emsp;&emsp;根据目标函数或者约束条件的不同，最优化问题可以有如下分类:<br>
&emsp;&emsp;&emsp;&emsp;* 连续/离散化优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 约束/非约束优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 线性/非线性优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 全局/局部优化问题<br>
&emsp;&emsp;&emsp;&emsp;* 随机/确定性优化问题<br>

## 四、凸优化
&emsp;&emsp;凸优化是优化问题中最基本的一种。实际中有很多问题都具有凸优化问题的特性，这种特性让问题更容易解。<br>
&emsp;&emsp;凸优化的几个概念:<br>
&emsp;&emsp;&emsp;&emsp;1. 凸集: 如果集合S为凸集，当且仅当 x∈S, y∈S 并且α(x)+(1−α)(y) inS;α∈[0,1]<br>
&emsp;&emsp;&emsp;&emsp;2. 凸函数：如果函数f(x)为凸函数，当且仅当S为凸集，x∈S, y∈S; αf(x)+(1−α)f(y)≥f(αx+(1−α)y); α∈[0,1]<br>
&emsp;&emsp;&emsp;&emsp;3. 严格凸函数，凸函数能够取到非等号，即α∈(0,1)<br>
&emsp;&emsp;&emsp;&emsp;4. 凸优化问题：对于标准形式目标函数为凸函数，等式约束为线性约束；不等式约束为凹函数。<br>

## 五、最优化算法
&emsp;&emsp;最优化算法是一个不断迭代的过程。起于一个初始参数(向量), 不断迭代改进预估值直至收敛，得到希望的解。<br>
&emsp;&emsp;一般好的优化算法有如下几个特性:<br>
&emsp;&emsp;&emsp;&emsp;1. 鲁棒性: 能在某类型的很多问题上都能有很好的解。<br>
&emsp;&emsp;&emsp;&emsp;2. 高效性: 能在有限的计算时间和存储内完成求解。<br>
&emsp;&emsp;&emsp;&emsp;3. 准确性: 能准确的求解问题，并且对数据中的错误不能过于敏感。<br>
&emsp;&emsp;上述的几个特性之间本身可能存在一定的矛盾，例如要鲁棒性很可能会比较慢。<br>
