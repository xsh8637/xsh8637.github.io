---
layout:     post
title:      "Numerical Optimization: INTRODUCTION"
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
&emsp;&emsp;&emsp;&emsp;投资组合最优: 高回报，低风险<br>
&emsp;&emsp;&emsp;自然界最优: 物理系统最低能量态<br>
&emsp;&emsp;&emsp;&emsp;...<br>
&emsp;&emsp;数值优化是通过迭代的方式解决最优化问题，是数学建模(modeling)的重要环节。<br>
&emsp;&emsp;Modeling需要确定优化目标、目标依赖的变量以及变量间的约束关系。<br>


## 二、算法原理
&emsp;&emsp;在基本概念中有说过，强化学习是一个反复迭代的过程，每一次迭代要解决两个问题：给定一个策略求值函数，和根据值函数来更新策略。<br>
&emsp;&emsp;DDPG中使用一个神经网络来近似值函数，此值函数网络又称critic网络，它的输入是 action与observation [s,a]，输出是Q(s,a)；另外使用一个神经网络来近似策略函数，此policy网络又称actor网络，它的输入是observation s，输出是action a.<br>
![](/images/2018-12-03-DDPG/DDPG.jpeg)
【我还没完。。。】
