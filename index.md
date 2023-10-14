# Hello World!



# 视觉SLAM

## <span id='jump'>最好直接完整clone项目</span>

```
git clone --recursive-submodules https://github.com/gaoxiang12/slambook2.git
```

安装所有依赖

```
sudo apt install -y libglew-dev libpng-dev python3-dev
```

重新编译安装

```
cd slambook2/3rdparty/Pangolin
mkdir build && cd build
cmake .. && make && sudo make install
```

编译ch3并运行

如果是使用[原作者的库](https://github.com/stevenlovegrove/Pangolin/)，需要先运行`./scripts/install_prerequisites.sh --dry-run recommended`安装依赖后编译安装



## ch3 

### git submodule update --init --recursive出错提示子模组未对路径注册

因为我使用的git url格式与原项目下的.gitmodule文件中的url格式不对，它写的是https格式，而我使用的是git的格式。

按照以下方法更换一下即可：

```
[submodule "3rdparty/Pangolin"]
	path = 3rdparty/Pangolin
	url = git@github.com:stevenlovegrove/Pangolin
[submodule "3rdparty/Sophus"]
	path = 3rdparty/Sophus
	url = git@github.com:strasdat/Sophus
[submodule "3rdparty/ceres-solver"]
	path = 3rdparty/ceres-solver
	url = git@github.com:ceres-solver/ceres-solver
[submodule "3rdparty/g2o"]
	path = 3rdparty/g2o
	url = git@github.com:RainerKuemmerle/g2o
[submodule "3rdparty/DBoW3"]
	path = 3rdparty/DBoW3
	url = git@github.com:rmsalinas/DBow3
[submodule "3rdparty/googletest"]
	path = 3rdparty/googletest
	url = git@github.com:google/googletest.git
```

子模块的url同步修改

```
$ git submodule sync
```

最后再来：

```
$ git submodule update --init --recursive
```

[最好直接完整clone项目](#jump)



### plotTrajectory.cpp

1. 添加#include<Eigen/Geometry>
2. string trajectory_file 需要更改



# typora下转跳到指定位置

第一种：
使用方括号[] 、(#锚点) 、a标签 、id 属性
点击点：

```
点击点：
[1、感冒了](#length)
调转到的点：
<a id="length">吃药休息</a>
```

第二种：

使用方括号[] 、(#锚点) 、span标签 、id 属性

```
点击点：
[2、问医生可以喝奶茶吗](#jump)
调转到的点：
<span id='jump'>医生说可以喝一点点</span>
```

