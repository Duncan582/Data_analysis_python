# Numerical methods
1. **FDM,FEM,FVM: Finite Difference/Element/Volumn Method**
FDM: 在离散规整十字网格简单计算导数
FEM: 三角化网格,残差加权在网格内积分为0
FVM: 封闭网格计算
2. **FDM**
使用正交网格,离散导数代替连续偏导,1D/2D精度高,具体直观实现简单,几何适应性弱
3. **FEM**
高门槛,适合复杂图形,几何适应性强,守恒性弱
4. **FVM**
通量边界守恒,在控制体积上积分,较高门槛,强守恒性，TCAD软件的核心之一就是守恒性
## 差分近似的基石:Taylor Expansion
1. **TruncationError截断误差**
舍弃的高阶项决定近似精度
2. **差分核心思维**
用邻近信息逼近计算导数(Taylor Expansion)
3. **差分方法**
- [ ] 一阶差分方法:前向,后向,中心差分都会产生误差,但中心差分精度较高 O(h^2)>O(h)
- [x] 二阶中心差分:对前向和后向差分再做一次差分或利用Taylor Expansion的二阶项
4. **FDM For Second Derivative**
矩阵特征:三对角结构[1, -2, 1]   极其稀疏,易储存
## Grid Discretization
1. **Single Dimension**
- 节点索引: x[i] = i * $\Delta$ x (均匀网格) 
- 函数值: $\phi$(i) = $\phi$(x[i])
## Matrix Formulation 
1. **Poisson formulation**
连续形式
2. **单点差分方程**
使用二阶中心差分,但出现边界处理问题
3. **边界处理**
PDE to Matrix: A @ x = b