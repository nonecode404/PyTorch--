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
  
  
