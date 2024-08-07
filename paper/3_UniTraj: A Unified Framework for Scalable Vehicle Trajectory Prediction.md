# UniTraj: A Unified Framework for Scalable Vehicle Trajectory Prediction
1. 摘要  


2. 引言  
- 作者提出了两个问题：1）当轨迹预测模型转换一个新的domain时性能可能会受影响； 2）数据集的容量增加对预测模型的性能有什么影响？  
- UNITRAJ统一了多种训练数据来源（nuscenes, argoverse, waymo open motion dataset），统一了模型(autobot, mtr, wayformer)。  
3. unitraj框架  
- 统一的data形式：作者使用ScenarioNet来统一处理数据。  
- 作者提出的改变主要包含：坐标系统、轨迹的时间长度、agent的特征、地图特征。  
- 统一的模型：  
autobot：基于transformer的模型，基于等变特征学习，利用多头注意力块学习轨迹的联合分布。  
mtr：将全局意图与局部运动细化相结合。  
wayformer：基于transformer的模型，