# Install Gym on Ubuntu20.04

### 1. 安装 Anaconda

在 Ubuntu 系统中安装 Gym 之前，建议先安装 Anaconda。See: https://www.anaconda.com/

Anaconda 自带 Jupyter Notebook，还自带了很多常用库，能方便地管理环境。

### 2. 利用 Anaconda 创建一个虚拟环境

```shell
conda create --name gymlab python=3.5
```
上面代码的意思是，创建一个名为 gymlab 的虚拟环境，用的是 python3.5 的版本（你可以按自己的需求设置）。

### 3. 安装 Gym

**1. 激活虚拟环境**

  ```shell
  conda activate gymlab
  ```
  
**2. 将openai/gym克隆至虚拟环境中**

  ```shell
  git clone https://github.com/openai/gym.git
  ```
  
**3. 安装gym依赖项**

  ```shell
  sudo apt-get install -y python-numpy python-dev cmake zlib1g-dev libjpeg-dev xvfb libav-tools xorg-dev python-opengl libboost-all-dev libsdl2-dev swig
  ```
  
  其中，libav-tools可能找不到，可以删除。
  
**4. 进入gym文件夹**

  ```shell
  cd gym
  ```
  
**5. 安装gym**

  See: https://github.com/openai/gym
  
  To install the base Gym library, use:
  ```shell
  pip install gym
  ```
  This does not include dependencies for all families of environments (there's a massive number, and some can be problematic to install on certain systems). 
  
  You can install these dependencies for one family like 
  ```
  pip install gym[atari]
  ```
  or use
  ```shell
  pip install gym[all] 
  ```
  to install all dependencies.
  
  对于本项目 biped_example，执行:
  ```shell
  pip install gym[box2d]
  ```
  
**6. 关于MuJoCo**

  把第3步中依赖都安装完以后，执行
  
  ```shell
  pip install gym[all] 
  ```
  
  还会有问题：
  ERROR: Failed building wheel for mujoco-py
  
  一种可能的解决方法如下：
  
  ```shell
  git clone https://github.com/openai/mujoco-py
  cd mujico-py
  pip install -e . --no-cache
  ```
  
  或者 See: https://blog.csdn.net/bornfree5511/article/details/107341116

### END
  
  
