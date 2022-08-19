# PyTorch--

## 第一章安装Pytorch

#### 安装Anaconda 
  1. 去官网并选择相应的系统下载。
  2. 检验是否安装成功，在程序启动项中查看是否生成了Anaconda Prompt
  
####  创建虚拟环境
  conda create -n env_name python==version
  相关命令：  
    安装包
    conda install package_name

    卸载包
    conda remove package_name

    显示所有安装的包
    conda list

    删除虚拟环境命令
    conda remove -n env_name --all

    激活环境命令
    conda activate env_name

    退出当前环境
    conda deactivate
    
####  换源
  可选择不换

#### 查看显卡型号
    需要查看本机显卡型号，找到适配的cuda版本。
    
#### 安装PyTorch
    该命令需要在虚拟机激活的环境下执行
    conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
    
    去掉-c pytorch 是用设置的源下载，不去掉是用官方源。如果网可以建议使用官方源。
    
#### 检验是否成功
    终端输入 python
    ```
    import torch
    torch.cuda.is_available()
    ```
    返回True即可
#### Pycharm适配
    setting-interpreter-add-cuda-exsting-选择自己创建的虚拟环境即可
    
## 基础知识

### 张量
  3维=时间序列，4维=图像，5维=视频
  
  张量的创建 rand zeros
  张量的操作 加法和索引
  广播机制 形状不同进行运算时
  
### 自动求导
  autograd核心包
  autograd的求导机制
  梯度的反向传播
  
  backwarddetach()
  
  输出导数 d(out)/dx
  
  grad在反向传播过程中是累加的(accumulated)，这意味着每一次运行反向传播，梯度都会累加之前的梯度，所以一般在反向传播之前需把梯度清零。
  
  并行计算
  
## 主要模块
  首先需要对数据进行预处理，其中重要的步骤包括数据格式的统一和必要的数据变换，同时划分训练集和测试集。接下来选择模型，并设定损失函数和优化方法，以及对应的超参数（当然可以使用sklearn这样的机器学习库中模型自带的损失函数和优化器）。最后用模型去拟合训练集数据，并在验证集/测试集上计算模型表现。
  
  ### 基本配置
    1. 导包
        import os
        import numpy as np
        import torch
        import torch.nn as nn
        from torch.utils.data import Dataset, DataLoader
        import torch.optim as optimizer
     超参数：
        batch_size = 16
        # 批次的大小
        lr = 1e-4
        # 优化器的学习率
        max_epochs = 100
   ### 数据读入
        batch_size：样本是按“批”读入的，batch_size就是每次读入的样本数

        num_workers：有多少个进程用于读取数据

        shuffle：是否将读入的数据打乱

        drop_last：对于样本最后一部分没有达到批次数的样本，使其不再参与训练
   
   ### 模型构建 
        PyTorch中神经网络的构造方法

        PyTorch中特殊层的构建

        LeNet的PyTorch实现
    
   ### 模型初始化
       一些相关函数的使用
       
   ### 损失函数
        二分类交叉熵损失函数
        交叉熵损失函数
        L1损失函数
        MSE损失函数
        平滑L1 (Smooth L1)损失函数
        目标泊松分布的负对数似然损失
        KL散度
        MarginRankingLoss
         多标签边界损失函数
         二分类损失函数
         多分类的折页损失 三元组损失
   ### 训练评估
        使用模型训练
        
  ## 基础实战
    1. 导包
    2. 环境和参数
    3. 数据读入和加载
    4. 设计模型
    5. 设定优化器 adam
    6. 训练测试
    7. 保存
      
  
  
