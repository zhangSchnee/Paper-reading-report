   按照第一周的计划上周我主要看了GCN的两篇paper中的理论和数学推导，理解了GCN的数学原理：GCN是CNN(卷积神经网络)在图这种非欧几里得空间数据结构上的推广。根据卷积的定义(两个函数的卷积等于两个函数频域乘积的逆变换)，人们根据拉普拉斯矩阵的性质构造出了傅里叶(逆)变换在graph上的形式，从而得到了图上的卷积神经网络的形式。
   
   实际上讲，一个信号的时域傅里叶变换的离散化表达就是信号向量和e^jwt向量的乘积加和，天然地满足矩阵形式。而e^jwt是广义的laplacian矩阵的特征向量，因此e^jwt映射到图上就是U(将laplaican做分解)。但是我们都知道算U很复杂，而几个主特征值已经可以较好的刻画U了，因此之后人们做的工作就是：能不能找到好的卷积核，从而使得计算U的复杂度下降(甚至不用算)等等；经过选用恰当的卷积核人们发现了一个虽然不是最优，但数学上看起来很舒服的一个形式：![](https://latex.codecogs.com/gif.latex?y&space;=&space;\sum_{j=0}^{K}\alpha_{j}L^jx)
   
   而巧妙的地方在于L\*x可以和热传导方程连上关系，图上节点信息量的变化不也是受到邻居节点、邻居的邻居...节点的影响嘛。
   
   和CNN一样，GCN也有局部节点的信息提取和参数共享，人们通过改变卷积核的大小来调节卷积核在图上感受野的范围。目前了解到的GCN理论研究重点是设计性质更加好的卷积核，使得计算量更小，更有效提取节点和边信息等。这周的计划是阅读一篇GCN应用到关系抽取的文章，看一看实际应用是怎样的。
