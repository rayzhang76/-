# -
统计学学习日记

如何用几个数字来描述一个数据集的特性？  

平均数，中位数，众数：  
平均数 = dataset.mean()，集合内所有样本数值相加然后除以样本个数  
中位数 = dataset.median()，集合内样本按照数值进行排序，取排位中间的数值。如果样本数为偶数，那么取排位中间的2个数的平均数  
众数mode，集合内数值取值相同的样本数值。众数可能有多个（比如2个或者多个），也可能没有(如果所有样本的unique个数一致)  

Range,数据集内最大值-最小值  
Mid-Range，数据集内 (max + min) / 2  
上述2个range类指标主要描述了数据集的边界特性，与数据集中其他样本没有关系  
