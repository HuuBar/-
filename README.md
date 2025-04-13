CNN图像分类项目（CIFAR-10）
概述
本项目使用PyTorch构建卷积神经网络（CNN），在CIFAR-10数据集上进行图像分类。代码包含数据加载、模型定义、训练、评估及结果可视化功能。

环境依赖
Python 3.6+

PyTorch 1.8+

torchvision

matplotlib

numpy

安装依赖：

bash
复制
pip install torch torchvision matplotlib numpy
数据集准备
项目使用CIFAR-10数据集。若默认路径 /bohr/cifar-p65r/v1/cifar-10-batches-py/ 不可用，需手动下载数据集：

从CIFAR-10官网下载Python版本数据集（cifar-10-python.tar.gz）。

解压至项目根目录，确保文件路径为 ./cifar-10-batches-py/。

使用步骤
1. 运行Jupyter Notebook
bash
复制
jupyter notebook
打开文件 CNN图像分类.ipynb。

2. 训练模型
修改训练轮数：在代码单元格 train_and_evaluate 函数调用处（需自行添加），设置 epochs 参数（默认未显式调用，需补充代码或直接运行现有训练循环）。

启动训练：依次执行所有代码单元格。训练过程中会输出每100个批次的损失值。

示例训练代码补充（在最后一个代码单元格前添加）：

python
复制
# 启动训练并评估
train_and_evaluate(net, trainloader, testloader, epochs=10)
3. 测试与结果可视化
训练结束后，代码会自动在测试集上计算准确率。

最后一组代码会随机展示测试集中的10张图像，并显示模型预测结果与真实标签的对比。

关键代码说明
数据加载：使用torchvision.datasets.CIFAR10加载数据集，并进行归一化处理。

模型结构：CNN包含3个卷积层和3个全连接层，使用ReLU激活函数和最大池化。

训练配置：优化器为Adam，学习率0.001，损失函数为交叉熵损失。
