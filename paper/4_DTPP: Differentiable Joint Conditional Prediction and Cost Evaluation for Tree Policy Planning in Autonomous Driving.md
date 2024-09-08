# DTPP: Differentiable Joint Conditional Prediction and Cost Evaluation for Tree Policy Planning in Autonomous Driving

1. 引言  
- 主要贡献：  
1） 提出了DTPP框架，能够与数据集进行联合训练，本文提出将预测和规划综合考虑。  
2） 提出一种以查询为中心，基于transformer的预测模型，该模型能够根据多个潜在的未来自我轨迹进行高效的多阶段运动预测。  
3） nuplan数据集中进行了闭环测试。  
2. 方法论  
- 两个关键的组件：以查询为中心的CMP模型使用transformer编码器提取环境上下文，并使用transformer编码器输出其他交通参与者的联合轨迹；成本评估模块以轨迹树和场景树作为输入计算每个分支的成本。  
- 构建轨迹树：使用车道为中心。生成以ego的多个参考路径。