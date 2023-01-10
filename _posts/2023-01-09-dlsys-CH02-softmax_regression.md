---
title: 'CMU10714 dlsys: CH02 softmax_regression'
date: 2023-01-09
permalink: /posts/2023/01/dlsys-CH02-softmax_regression/
tags:
  - dlsys
Categories:
  - course
---

# 02 ML Refresher / Softmax Regression

[CH02课件](https://dlsyscourse.org/slides/softmax_regression.pdf)

[CH02课堂视频](https://www.youtube.com/watch?v=MlivXhZFbNA)

## 2.1 机器学习基础知识

- **机器学习算法**：三大组成要素。大部分机器学习算法均指定不同的此三部分，形成了不同算法。
  1. **假设函数 / 目标函数 hypothesis class**：通过参数指定映射的输入输出
  2. **损失函数 loss function**：在任务中描述目标函数如何表现良好
  3. **优化过程 optimization method**：优化参数使最小化训练集的损失和

## 2.2 多类逻辑回归 Softmax Regression

- **设定**：$x^{(i)}\in R^n,\quad y^{(i)}\in \{1,...,k\}\text{  for  } i=1,...,m$
  
  - 输入向量维度 $n$ ，类别数 $k$ ，训练样本数 $m$
  
- **线性假设函数**：通常 $h:R^n\longrightarrow R^k$，因此线性假设函数为
  
  $$
  h_{\theta}(x)=\theta^Tx \qquad\text{ for }\;\theta\in R^{n\times k}
  $$

- **矩阵批处理符号**：
  
  - **设定**：
    $$
    X\in R^{m\times n}=\begin{bmatrix}{x^{(1)}}^{T}\\ \vdots \\{x^{(m)}}^{T}  \end{bmatrix},\qquad y\in \{1,...,k\}^m =\begin{bmatrix}y^{(1)}\\ \vdots \\y^{(m)}  \end{bmatrix}
    $$
  
  - **改写**：
    $$
    h_{\theta}(X) = \begin{bmatrix}h_{\theta}{(x^{(1)})}^{T}\\ \vdots \\h_{\theta}{(x^{(m)})}^{T}  \end{bmatrix} = \begin{bmatrix}{x^{(1)}}^{T}\theta\\ \vdots \\{x^{(m)}}^{T}\theta  \end{bmatrix} = X\theta
    $$
  
- **损失函数**：

  1. **01损失（Classification Error）**：利于量化分类器的性能，但对实际优化参数很不利（不可微分）
     $$
     l_{err}(h(x),y)=\begin{cases}0\quad \text{if}\; \arg\max_i\;h_i(x)=y \\1\quad \text{otherwise} \end{cases}
     $$

  2. **交叉熵损失（Softmax / Cross-Entropy Loss）**：

     - **Softmax转换**：求幂+归一化（使变正数并归一），在输出和概率间进行映射

     $$
     z_i=p(\text{label}=i)=\dfrac{\exp(h_i(x))}{\sum\limits_{j=1}^{k}\exp(h_j(x))}\iff z\equiv\text{normalize}(\exp(h(x)))
     $$

     - **负对数损失**：量化损失，使得真实类别的损失要小

     $$
     l_{ce}(h(x),y)=-\log p(\text{label}=y)=-h_y(x)+\log\sum\limits_{j=1}^{k}\exp(h_j(x))
     $$

     - **注意**：将交叉熵损失应用于线性假设函数，而不是将负对数损失应用于softmax概率


- **优化问题**：
