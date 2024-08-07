# VectorNet: Encoding HD Maps and Agent Dynamics from Vectorized Representation

1. 摘要  
这篇文章主要引入vectorNet，使用GNN向量化表示和建模。使用cnn向量化表示agents的轨迹和道路结构。  
2. 引言  
- 提到使用`节点的空间和语义近似性`很重要。
- 所有的线使用全连接去交换信息。  
- 局部图使用MLP，全局图使用self-attention。
3. VectorNet approach
- 提出了向量化agent轨迹和HD地图的方法  
- 对轨迹来说按照0.1s的间隔采样能够近似表示agent的轨迹。  
- 每个向量的表达如下  
$$
v_i=[d_i^s, d_i^e, a_i, j]  
$$
分别代表start and end points；$a_i$代表特征，比如object type, timestamps for trjectories, road type, speed limit for lanes； j是子图id。  
- 子图  
$$
v_i^{l+1}=\psi _{rel}(g_{enc}(v_i^{l}, \psi_{agg}(\{g_{enc}(v_j^{(l)})\})))
$$
$v_i^{l}$是第l层的子图网络，$g_{enc}()$是一个MLP，$\psi_{agg}()$从所有的邻居节点中收集信息，$\psi()$是节点$v_i$和邻居节点的操作。

- `global graph`:  
使用GNN的方法，MLP作为decoder函数。第p个节点特征表示如下。  
$$
\{p_i^{(l+1)}\}=GNN({p_i^{(l)}}, A)
$$
GNN对应一个单层gnn，A对应字节点的邻接矩阵(adjacency matrix)。  
3. 训练  
MLP的隐藏层是64，使用了layer normalization 和relu非线性。学习率每5个epochs使用减少因子0.3，作者训练模型使用了25个epoch，初始学习率为0.001.  
4. 展望  
vectornet是单模态轨迹。  
ADE DE@1S是什么指标？