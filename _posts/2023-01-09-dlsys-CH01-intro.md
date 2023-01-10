---
title: 'CMU10714 dlsys: CH01 intro'
date: 2023-01-09
permalink: /posts/2023/01/dlsys-CH01-intro/
tags:
  - dlsys
Categories:
  - course
---

# 01 Introduction and Logistics

[CH01课件](https://dlsyscourse.org/slides/intro_online.pdf)

[CH01课堂视频](https://www.youtube.com/watch?v=ftP5HeOvsI0)

## 课程介绍

- 你将学到：自动积分(automatic differentiation)，神经网络架构(neural network architectures)、优化(optimization)、在GPU上高效操作
  1. 现代DL库的基本功能（包括自动积分，基于梯度的优化）
  2. 只用python实现几个标准DL框架（MLPs，ConvNets, RNNs, Transformers）
  3. 实施硬件加速的底层工作原理，能够高效开发代码
- 作业：开发Needle库——实现许多通用结构。
- 为什么学本课：
  1. 目前dlsys（例：Pytorch，TensorFlow，JAX）研究还没到头
  2. 学dlsys（底层原理）有助于更有效使用它们
  3. 很酷：核心代码简单，2000行就可在GPU上跑卷积网络等