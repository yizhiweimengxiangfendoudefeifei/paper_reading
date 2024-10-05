# EPSILON: An Efﬁcient Planning System for Automated Vehicles in Highly Interactive Environments

1. 摘要  
- 摘要结介绍了使用POMDP做决策，使用SSC生成舒适、安全的轨迹。  
2. 系统框架  
- 动静态障碍物被建模通过SSC方法，其次使用了piece-wise bezier曲线优化方法生成轨迹。  
3. 问题定义  
- POMDP模型定义  
hidden states被评估使用观察，这有点类似预测，因此在epsilon中没有预测。  
- 为什么使用POMDP？  
人类驾驶员在开车的时候不会在脑海中设置lattice网格，通常只会有几个状态机组成（lane keeping, yield, overtaking等）。pomdp类似于后者。  
- 相对于MPDM有什么优势？  
考虑了更多的未来决策行为，因此pomdp包含更加复杂的运动。
4. 使用SSC生成轨迹  
- 使用bp层的最终决策包含了ego和其他车辆的一些列状态$[x_{t+1}, x_{t+2}, ..., x_{t+H}]$


小记：  
决策的综述：Planning and decision-making for autonomous vehicles  