# Wayformer: Motion Forecasting via Simple & Efﬁcient Attention Networks  

1. 贡献  
这篇文章主要提出了三种方法：  
- self-attention encoder，在时间和空间维度上添加了更多的模态；cross-attention decoder，关注驾驶场景元素能够产生多种轨迹。  
- 研究了场景encoder的三种不同变体，在不同的输入模态以及何时融合存在差异。  
- 两种常用的技巧加速self-attention：factorized attention and latent query attention。  
2. 多模态场景理解  
- agent历史，包含一系列过去的状态$[A,T,1,D_h]$  
- agent 交互，和周围环境的交互，$[A,T,S_i,D_i]$，$S_i$代表周围环境的物体，$D_i$代表每个agent的状态。  
- roadgraph， $[A,1,S_r, D_r]$: roadgraph使用线段近似代替road的形状，没有时间维度，时间设置为1.  
- traffic light state，$[A,T,S_{tls}, D_{tls}]$包含最接近那个agent的交通灯信号。  
3. 融合  
- late fusion：  
- early fusion：  
- hierarchical fusion：  
4. attention  
- Multi-Axis Attention，时间计算复杂度$O(S_m^2 * T^2)$  
- Factorized Attention：  
5. 缺点  
1） ego为坐标原点需要大量计算量。  
2） 系统的输入是稀疏状态表达，难以捕捉一些细节特征，比如说：车辆前轮转角、行人转头等。  
3） 对每个agent建模表达未来的轨迹。
