# Hello World!



# 视觉slam

<details>
    <summary>
        <b><font face="微软雅黑" color="black" size="6.8" >笔记</font>
    </summary>


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

</details>



# Tips

<details><summary><b><font face="微软雅黑" color="black" size="6.8" >Typora跳转</font></summary>


## 第一种跳转：

使用方括号[] 、(#锚点) 、a标签 、id 属性
点击点：

```
点击点：
[1、感冒了](#length)
调转到的点：
<a id="length">吃药休息</a>
```

## 第二种跳转：

使用方括号[] 、(#锚点) 、span标签 、id 属性

```
点击点：
[2、问医生可以喝奶茶吗](#jump)
调转到的点：
<span id='jump'>医生说可以喝一点点</span>
```

</details>



<details><summary><b><font face="微软雅黑" color="black" size="6.8" >Typora转html时的多折叠问题</font></summary>

## 第一种折叠

在第一段折叠结束后输入强制回车

```
<bp>
```

这样后面的html代码可以多行输入

## 第二种折叠

html代码输入在同一行



<details><summary><b><font face="微软雅黑" color="black" size="6.8" >LaTeX论文</font></summary>

## TeXLive+TeXstudio win10

**LaTeX的使用需要2个重要东西：1.**选择一个TeX发行版进行安装（根据个人系统，本文选择**Texlive Win10**）。**2.**选择合适的Latex编辑器（如CTex的Winedt,本文选择**Texstudio**）

本人下载的TeXlive是最新版的（如下图），下载地址：[清华Texlive镜像](https://link.zhihu.com/?target=https%3A//mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)。安装程序为texlive2021-20210325.iso。

![img](https://pic1.zhimg.com/80/v2-84b642024f2f613f1b519ec4c6c54800_1440w.jpg)

**安装步骤：**

**1. 解压Texlive2021-20210325.iso文件，右键install-tl-windows.bat,以管理员身份打开。**

![img](https://pic2.zhimg.com/80/v2-349df902cb16a7da9b2ccc4b52f26821_1440w.jpg)

**2. 出现如下界面，点击 Advanced。**

![img](https://pic2.zhimg.com/80/v2-0844260d0756bab78f9f7bc06a277b95_1440w.webp)

**3. 选择安装位置，其他保持默认，并点击安装**

![img](https://pic1.zhimg.com/80/v2-dd788de434dcb737f781fa4aebe5191c_1440w.webp)

**4. 出现如下界面，等待ing**

![img](https://pic1.zhimg.com/v2-4545a3ef117ae522459cf5fe39f535b6.jpg?source=25ab7b06)

**5. 安装完成**

![img](https://pic3.zhimg.com/80/v2-6bb1b34bd26265858969ddad2534949a_1440w.webp)

**6. 最后打开cmd,分别输入tex -v, latex -v, xelatex -v, pdflatex - v 出现版本号证明安装成功！！！**

-> tex -v

![img](https://pic3.zhimg.com/80/v2-aa4be97ef416102d5f78c6677b850fca_1440w.webp)

-> latex -v

![img](https://pic2.zhimg.com/80/v2-8effa6cec4c2110ba7062ebf220cfd71_1440w.webp)

-> xelatex -v

![img](https://pic4.zhimg.com/80/v2-373afb148f20f9982114861113bb91fb_1440w.webp)

-> pdflatex - v

![img](https://pic3.zhimg.com/80/v2-12e9d61e189d888a6b23ea9ec608322e_1440w.webp)

------

**三、TeXStudio安装**

**1**. **安装 按照下面步骤进行安装（很简单）TexStudio下载地址：**[TeXStudio](https://link.zhihu.com/?target=http%3A//texstudio.sourceforge.net/)

![img](https://pic4.zhimg.com/80/v2-43d1f9119eb142130b062399bb34daaf_1440w.webp)

![img](https://pic3.zhimg.com/80/v2-7a6b796cfdd867171988bc2764988f62_1440w.webp)

![img](https://pic3.zhimg.com/80/v2-776eaae33bc5eae32980c1bb2e7b1616_1440w.webp)

**2. 配置**

**接下来就是TeXstudio的配置。**

**2.1 将语言设置为中文。依次选择Opitions->Configure TeXstudio**

![img](https://pic4.zhimg.com/80/v2-dc53ab7ae21630b4d26d9cd0899d063b_1440w.webp)

**2.2 修改中文界面后，我们可以选择左侧命令设置不同编译器，外部PDF查看器，和参看文献的执行程序。**

点击1处，可以将上述提到的3，4，5等的路径设置为TeXlive安装路径下对应的exe执行程序。点击2处，就可恢复默认。

![img](https://pic1.zhimg.com/80/v2-5816e83f47ec8543d27ac53e2e85d074_1440w.webp)

**2.3 默认编译器、默认PDF查看器、默认文献工具等设置**

点击构建选项，可以修改默认编译器、PDF查看器和默认文献工具等。若写中文论文，则需修改默认编译器为XelaTeX. 若为英文，则用PdfLaTex。

![img](https://pic2.zhimg.com/80/v2-ffca3f2ebefcca32bbd5a6e014edc3f5_1440w.webp)

**2.4 设置默认字体编码和添加行号**

点击编辑器选项，一般默认字体编码为UTF-8（一般不修改）。显示行号默认：所有行号。添加行号，可以快速定位某个词或句的位置。此外，当程序报错时，可快速定位到出错位置，方便修改。

![img](https://pic2.zhimg.com/80/v2-c668cc7e5074376c0335d529b1084cfd_1440w.webp)

![img](https://pic3.zhimg.com/80/v2-0db0b5dc663a59c2523eb4dadc65b162_1440w.webp)

**小结：TeXstudio的配置就介绍到这里，如有其他配置，可根据自己需求设定，也可在评论区区留言。**

**3. TeXstudio中英文测试**

输入下面代码（含中文），选择默认编译器为XeLateX（选择PDFLeteX会报错），点击编译并查看按钮（或F5快捷键），查看效果。

```tex
\documentclass[11pt]{ctexart}  
\usepackage[top=2cm, bottom=2cm, left=2cm, right=2cm]{geometry}  
\usepackage{algorithm}  
\usepackage{algorithmicx}  
\usepackage{algpseudocode}  
\usepackage{amsmath}  

\floatname{algorithm}{算法}  
\renewcommand{\algorithmicrequire}{\textbf{输入:}}  
\renewcommand{\algorithmicensure}{\textbf{输出:}}  

\begin{document}  
    \begin{algorithm}  
        \caption{用归并排序求逆序数}  
        \begin{algorithmic}[1] %每行显示行号  
            \Require $Array$数组，$n$数组大小  
            \Ensure 逆序数  
            \Function {MergerSort}{$Array, left, right$}  
            \State $result \gets 0$  
            \If {$left < right$}  
            \State $middle \gets (left + right) / 2$  
            \State $result \gets result +$ \Call{MergerSort}{$Array, left, middle$}  
            \State $result \gets result +$ \Call{MergerSort}{$Array, middle, right$}  
            \State $result \gets result +$ \Call{Merger}{$Array,left,middle,right$}  
            \EndIf  
            \State \Return{$result$}  
            \EndFunction  
            \State  
            \Function{Merger}{$Array, left, middle, right$}  
            \State $i\gets left$  
            \State $j\gets middle$  
            \State $k\gets 0$  
            \State $result \gets 0$  
            \While{$i<middle$ \textbf{and} $j<right$}  
            \If{$Array[i]<Array[j]$}  
            \State $B[k++]\gets Array[i++]$  
            \Else  
            \State $B[k++] \gets Array[j++]$  
            \State $result \gets result + (middle - i)$  
            \EndIf  
            \EndWhile  
            \While{$i<middle$}  
            \State $B[k++] \gets Array[i++]$  
            \EndWhile  
            \While{$j<right$}  
            \State $B[k++] \gets Array[j++]$  
            \EndWhile  
            \For{$i = 0 \to k-1$}  
            \State $Array[left + i] \gets B[i]$  
            \EndFor  
            \State \Return{$result$}  
            \EndFunction  
        \end{algorithmic}  
    \end{algorithm}  
\end{document}
```

**XeLateX编译器（未报错）**：

![img](https://pic4.zhimg.com/80/v2-7fdec8e409eb2fec19d94194c0218987_1440w.webp)

**PDFLaTeX编译器（报错）**：

![img](https://pic1.zhimg.com/80/v2-76d63763e78403fcad3466da80bd3bfc_1440w.webp)

输入下面代码（**只有英文**），编译器XeLaTeX/PDFLeTeX都可，点击编译并查看按钮（或F5快捷键），查看效果。（**注：代码太长，已附件形式显示**）

![img](https://pic3.zhimg.com/80/v2-df6dc4b3fe5469e38f8a58544ec9a58a_1440w.webp)

