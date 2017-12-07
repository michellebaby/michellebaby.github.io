---
layout: post
title: TensorFlow实现wgan-gp with text填坑指南
categories: Machine-Learning
tags: Machine-Learning Tensorflow
author: Kaiyu
---


* content
{:toc}

最近在实现基于TensorFlow的wgan—gp在text上的应用，最开始是直接clone的github的代码([improved version of wgan]) 但是在实现中发现代码是基于gpu实现的，但是自己又没有gpu，issue里面也没有可行的解决办法。因此就自己动手开始修改代码。开始发现报错是在conv1d里面的返回result出错：NCHW格式只支持gpu模式，因此改成NHWC，但是发现唯独不一致问题。因此在conv1d中判断维度，然后tranpose即可解决。但是自己是TensorFlow和机器学习的萌新。也不知道这样会不会修改了实现逻辑，而且也不知道为什么会报这个错误。


##  暂时就这些了！

[improved version of wgan]:https://github.com/igul222/improved_wgan_training