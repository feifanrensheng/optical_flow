基于Gauss-Newton的金字塔光流法
主要包括下面四种实现，forward-addtive Gauss-Newton 光流的实现。先考虑单层图像的 LK 光流,
然后再推广至金字塔图像。我们把光流法建模成一个非线性优化问题,再使用 Gauss-Newton 法迭代求解。
window为8*8大小的小块。
在Gauss-Newton的迭代过程中，error对自变量的求导Jacobian矩阵为对像素梯度的计算。分为两种
Forward Jacobian：计算I2(x+dx,y+dy)的梯度（总处于变化中）
Inverse Jacobian：计算I1(x,y)的梯度，不随迭代改变，只需计算一次，可以在后续迭代中一直使用，节省计算时间
OpticalFlowSingleLevel 函数添加一个 bool inverse 参数,指定要使用正常的算法还是反向的
算法

