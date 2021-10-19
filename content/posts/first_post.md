---
title: "Center Selection Algorithm"
date: 2021-10-13T19:42:48+08:00
draft: false
author: "wenlewei"
---
<center><font size =5>Center Selection Algorithm</font></center>
<font face="黑体">&emsp;&emsp;In the k-means algorithm, we can start with (i) using an initial partition {S1, S2, ..., Sk} or with (ii) using initial centers {c1, c2, ..., ck}. Design a good initialization method for k-means algorithm for (i) and also for (ii)
 
</font>
<font face="黑体"> 

 &emsp;&emsp;题目相当于问k-means方法的初始化。常规的来说有三种方法，第一种随机选择初始点，第二种k-means++，第三种基于层次的初始化。对于聚类初始化算法来说，其效率很大程度上是跟其初始数据有关的，所以很难说某种算法非常的优秀，但总体上来说，k-means++应该是使用最广泛的一种。  
 &emsp;&emsp;首先来讲一下kmeans++算法  
 1、随机选取第一个中心  
 2、计算每个样本和已有聚类中心的最短距离。下一个中心被选中的概率与这个最短距离的平方成正比。D(x<sub>i</sub>)=min||x<sub>i</sub>−c<sub>r</sub>||<sup>2</sup> 其中D(x<sub>i</sub>)越大，选中概率越大。  
 3、然后一直重复第二个步骤，直到选出K个中心点来。
![avater](https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/initial%201.jpg)
 

