# Install Gym on Ubuntu20.04

### 1. Install Anaconda

Before installing Gym, it is recommended to install Anaconda first. See: https://www.anaconda.com/

Anaconda comes with *Jupyter Notebook*, and also comes with many commonly used libraries, which can easily manage the environment.

### 2. Create a virtual environment with Anaconda

```shell
conda create --name gymlab python=3.6
```

### 3. Install Gym

**1. Activate the virtual environment**

  ```shell
  conda activate gymlab
  ```
  
**2. Clone openai/gym into the virtual environment**

  ```shell
  git clone https://github.com/openai/gym.git
  ```
  
**3. Install some dependencies for Gym**

  ```shell
  sudo apt-get install -y python-numpy python-dev cmake zlib1g-dev libjpeg-dev xvfb libav-tools xorg-dev python-opengl libboost-all-dev libsdl2-dev swig
  ```
  
  Among them, libav-tools may not be found and can be deleted.
  
**4. Enter the gym folder**

  ```shell
  cd gym
  ```
  
**5. Intall your gym**

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
  
  **For this project** *biped_example*, use:
  ```shell
  pip install gym[box2d]
  ```
  
**6. About MuJoCo**

  After installing all the dependencies in step 3, when you execute
  
  ```shell
  pip install gym[all] 
  ```
  
  There will be problems: 
  ERROR: Failed building wheel for mujoco-py
  
  One possible solution is as follows:
  
  ```shell
  git clone https://github.com/openai/mujoco-py
  cd mujico-py
  pip install -e . --no-cache
  ```

### END and ENJOY
