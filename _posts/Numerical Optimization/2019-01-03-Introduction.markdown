---
layout:     post
title:      "数值优化_序"
subtitle:   "Numerical Optimization: INTRODUCTION"
date:       2019-01-03 19:30:00
author:     "Thomas"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数值优化
    - Numerical Optimization
---

> “DDPG是Actor-Critic结构的model free & off-policy的方法.”


## 一、概述

&emsp;&emsp;DDPG (Deep Deterministic Policy Gradient)算法是model free（无环境模型）, off-policy（产生行为的策略和进行评估的策略不一样）的强化学习算法，且使用了深度神经网络用于函数近似。DDPG可以解决连续动作空间问题，属于actor-critic方法，即既有值函数网络(critic)，又有策略网络(actor)。<br>
&emsp;&emsp;DDPG算法原文链接：<a href="https://arxiv.org/pdf/1509.02971.pdf" target="_blank" rel="external">DDPG</a>

## 二、算法原理
&emsp;&emsp;在基本概念中有说过，强化学习是一个反复迭代的过程，每一次迭代要解决两个问题：给定一个策略求值函数，和根据值函数来更新策略。<br>
&emsp;&emsp;DDPG中使用一个神经网络来近似值函数，此值函数网络又称critic网络，它的输入是 action与observation [s,a]，输出是Q(s,a)；另外使用一个神经网络来近似策略函数，此policy网络又称actor网络，它的输入是observation s，输出是action a.<br>
![](/images/2018-12-03-DDPG/DDPG.jpeg)
【我还没完。。。】
