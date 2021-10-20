# Center Selection Algorithm

<center><font size =5>Center Selection Algorithm</font></center>
<font face="黑体">&emsp;&emsp;In the k-means algorithm, we can start with (i) using an initial partition {S1, S2, ..., Sk} or with (ii) using initial centers {c1, c2, ..., ck}. Design a good initialization method for k-means algorithm for (i) and also for (ii)
 
</font>
<font face="黑体"> 

 &emsp;&emsp;题目相当于问k-means方法的初始化。常规的来说有三种方法，第一种随机选择初始点，第二种k-means++，第三种基于层次的初始化。对于聚类初始化算法来说，其效率很大程度上是跟其初始数据有关的，所以很难说某种算法非常的优秀，但总体上来说，k-means++应该是使用最广泛的一种。  
 &emsp;&emsp;首先来讲一下kmeans++算法  
 &emsp;&emsp;1、随机选取第一个中心  
 &emsp;&emsp;2、计算每个样本和已有聚类中心的最短距离。下一个中心被选中的概率与这个最短距离的平方成正比。D(x<sub>i</sub>)=min||x<sub>i</sub>−c<sub>r</sub>||<sup>2</sup> 其中D(x<sub>i</sub>)越大，选中概率越大。  
 &emsp;&emsp;3、然后一直重复第二个步骤，直到选出K个中心点来。  
&emsp;&emsp;然后说一下我的方法，我选择第一个中心点的时候不是随机选择，而是想选择密度大的中心点。所以我计算了每一个点到其他点距离的总和，并将总和最小的那个点，作为我的初始点。然后就是选择离已选择中心尽可能远的点，与k-mean++的思想类似，但是没有用轮盘法来进行选择。  

![avater](https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/initial%20step.jpg)  
下面是我简单举例展示出我的初始化和随机初始化的区别。  
首先是随机初始点，设置k值为2，橙色和蓝色点为随机生成的初始点，然后按照k-means算法进行聚类。  

<img src="https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/initial%201.jpg" width="300" height="250">
<img src="https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/initial%202.jpg" width="300" height="250">    
<p style="font-size:14px;color:#C0C0C0;align="left">&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;初始点设置&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;迭代第一次</p>  

随机生成初始点后，用k-means算法迭代了三次达到了收敛。  

<img src="https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/initial%203.jpg" width="300" height="250">
<img src="https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/initial%204.jpg" width="300" height="250">
<p style="font-size:14px;color:#C0C0C0;align="left">&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;迭代第二次&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;迭代第三次</p>  

然后是用我的方法进行初始化，橙色的点是由我计算与其他点距离总和最小的点得到的，然后是选距离已有中心最远的点，就是蓝色的点。然后到k-means收敛，只迭代了一次。  
  
<img src="https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/myinitial%201.jpg" width="300" height="250">
<img src="https://raw.githubusercontent.com/cocowenlw/blog-picture/master/hugo/myinitial%202.jpg" width="300" height="250">
<p style="font-size:14px;color:#C0C0C0;align="left">&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;初始点设置&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;迭代第一次</p>


