# -
统计学学习日记

统计学可以从2个方面来学习：  
Descriptive, 描述性, 以一些关键性的指标来表述统计特征  
Inferancial, 推论性, 进行推导计算  

Descriptive:  
如何用几个数字来描述一个数据集的特性？ 答案：Central tendency/集中性趋势和Dispersion/散布  

Central Tendency, 集中性趋势描述可以用下面几个指标:  
平均数 = dataset.mean()，集合内所有样本数值相加然后除以样本个数  
中位数 = dataset.median()，集合内样本按照数值进行排序，取排位中间的数值。如果样本数为偶数，那么取排位中间的2个数的平均数  
众数mode，集合内数值取值相同的样本数值。众数可能有多个（比如2个或者多个），也可能没有(如果所有样本的unique个数一致)  
中位数和众数可以解决"被平均"的问题，阻止个别离群点对整个数据集描述造成有偏离的印象  

引入新的概念: 
population 完整数据集  
sample 完整数据集的一个子集  
对应的有sample mean和population mean  
引入新的公式记述方式  Sum  

Dispersion ,数据的散布  
Population Variance, 方差  sum((xi-u) * (xi-u)) / N  
Sample Variance, sum((xi-u) * (xi-u)) / (n-1)  
我可以理解，如果sample variance使用与population一样的公式，有较大概率Variance被低估。但是也有可能被高估呀？而且为什么分母要改为n-1而不是n-2或者任意的其他一个数字？  
standard Variance 标准差  在方差基础上做一个平方根操作, 好处是数据的单位变得一致了。  
推导population variance方差的简化计算方式：sum(xi * xi)/N - u * u

随机变量与二项式:  
n = 总次数，m = x=1的次数  
P(x=m) = n!/(m! * (n-m)!) * power(P1,n)  
这里视频上写的公式似乎出错了  
抛5次硬币得到一个粗略的概率曲线，抛500万次硬币（近似连续取值）得到一个bell curve或者normal distribution(正态分布)  

当0/1概率不再是55开的时候，公式更加有趣了：  
P(x=m) = n!/(m! * (n-m)!) * power(P1,m) * power(P0,(n-m))  
当P0=P1的时候，公式又回到上面例子的形式  

E(X), 随机变量的期望值 = X取值 * P(X)  
数值上等同于均值(population mean)  

当success几率为P的时候，N次试验后的成功次数的期望值E = p * n  
（就是这么简单，当然还需要证明一下。绕了一大圈，还用了换元法）  

假设我们需要统计1小时内经过某地的车辆数目，可以先数车数小时，然后得到一个车辆经过的期望值E(X) = a  
np = E(X) = a ==> p = a/n  
假设n代表60分钟，那么P(X=K） = C(60,K) * power(a / 60, K) * ( 1- a/60, 60-k)  
从1分钟通过多辆车，或者1秒钟通过多辆车，引出n==>无穷的情况，引出泊松分布  
P(X=k) = power(a,k) / k! * power(e, -a)  
泊松分布的计算涉及到极限计算，这个中间过程涉及到2个简化项，还需要特别复习一下  

大数定律：  
当n-->无穷大的时候，sample mean --> population mean  
这里要注意一个赌徒谬论，gambler fallacy。大数定律的关键在于infinite而不是均值回归  


Range,数据集内最大值-最小值  
Mid-Range，数据集内 (max + min) / 2  
上述2个range类指标主要描述了数据集的边界特性，与数据集中其他样本没有关系  
