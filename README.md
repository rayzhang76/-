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

推到population variance方差的简化计算方式：sum(xi * xi)/N - u * u


Range,数据集内最大值-最小值  
Mid-Range，数据集内 (max + min) / 2  
上述2个range类指标主要描述了数据集的边界特性，与数据集中其他样本没有关系  
