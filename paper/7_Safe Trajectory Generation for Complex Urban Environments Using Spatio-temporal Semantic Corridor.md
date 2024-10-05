# Safe Trajectory Generation for Complex Urban Environments Using Spatio-temporal Semantic Corridor

2. related works  
- ziegler提出时空lattice采样方法，由于lattice方法的维度灾难，有人提出利用gpu进行加速（“Motion plan-
ning for autonomous driving with a conformal spatiotemporal lattice）。  
3. MPDM（multi-policy decision making）  
- 该方法使用pomdp和动态环境建模和交互。建模时简化了问题，假定他车和自车的状态有限，policy包含：lane change, lane keeping  
- mpdm总是为自车准备了三种状态，包含lc right, lc left, lk。  