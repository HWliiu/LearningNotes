### 傅里叶级数推导

[TOC]

##### 傅里叶级数推导

[傅里叶系列（一）傅里叶级数的推导 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/41455378)

**任何连续周期信号都可以由一组适当的正弦曲线组合而成**

<img src="Fourier.assets/image-20211009170919225.png" alt="image-20211009170919225" style="zoom:67%;" />

推导：

<img src="Fourier.assets/image-20211009170958112.png" alt="image-20211009170958112" style="zoom:67%;" />

（这里$w$衡为1，因为$w$是角频率，$w=\frac{2\pi}{T}$,而$f(t)$的周期$T=2\pi$. $A_0$是直流分量）	

<img src="Fourier.assets/image-20211009171046204.png" alt="image-20211009171046204" style="zoom: 50%;" />

<img src="Fourier.assets/image-20211009171115377.png" alt="image-20211009171115377" style="zoom:67%;" />

> **三角函数的正交性质**
>
> <img src="Fourier.assets/image-20211009171139914.png" alt="image-20211009171139914" style="zoom:67%;" />
>
> （$n$必须是整数才能满足正交性质）

<img src="Fourier.assets/image-20211009172434102.png" alt="image-20211009172434102" style="zoom: 67%;" />

两边同乘$\cos(kwt)$:

<img src="Fourier.assets/image-20211009172213985.png" alt="image-20211009172213985" style="zoom: 67%;" />

<img src="Fourier.assets/image-20211009172856369.png" alt="image-20211009172856369" style="zoom: 67%;" />

<img src="Fourier.assets/image-20211009172932995.png" alt="image-20211009172932995"  />

<img src="Fourier.assets/image-20211010101402348.png" alt="image-20211010101402348" style="zoom:50%;" />

###### 时域$\to$频域

<img src="Fourier.assets/4695ce06197677bab880cd55b6846f12_1440w.jpg" alt="img" style="zoom: 33%;" />

---

##### 连续傅里叶变换

[傅里叶系列（二）傅里叶变换的推导 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/41875010)

[从傅立叶级数到傅立叶变换 - 马同学 (matongxue.com)](https://www.matongxue.com/madocs/712/)

[傅里叶分析（完整版）更新于2014.06.06 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/19763358)

**连续傅里叶变换**，默认指的是**连续非周期信号**的变换。因为非周期信号可以想象成信号的周期趋近于无穷大，所以傅里叶变换其实是对傅里叶级数的扩展。

时域分解得到的正弦函数的频率ω1，ω2，ω3等，我们取他们的**最大公约数**，（这个地方说最大公约数似乎有些不合适，就是表示选取的数能把ω1们整除）然后把它命名为ω，它就是我们给这个频域图像选取的‘基’，通俗地讲就是所谓的“单位一”，有了这个基，我们就可以吧频域上的刻度写成1,2,3,4······

$w$是基频率，当$T \to + \infty$时，$\Delta w=(n+1)w-w$，$\Delta w\to 0$

<img src="Fourier.assets/image-20211011091218890.png" alt="image-20211011091218890" style="zoom:50%;" />

**傅立叶变换的4种变体：**

![image-20211011174431263](Fourier.assets/image-20211011174530892.png)

###### 傅里叶级数指数形式

<img src="Fourier.assets/image-20211010100903367.png" alt="image-20211010100903367" style="zoom: 50%;" />

<img src="Fourier.assets/image-20211010101155324.png" alt="image-20211010101155324" style="zoom:50%;" />

<img src="Fourier.assets/image-20211010104012572.png" alt="image-20211010104012572" style="zoom:50%;" />

（三角函数形式时$n\in [1,+\infty),n \in Z$，转为指数形式后$n\in (-\infty,+\infty),n \in Z$）

###### 从向量的角度看傅里叶级数

> *（另一篇博客的截图，符号定义有变化）*
>
> 指数形式：
>
> <img src="Fourier.assets/image-20211011091956909.png" alt="image-20211011091956909" style="zoom:50%;" />
>
> 因为基$e^{iwnx},n\in\mathbb{N}$实际上反映了周期运动的频率，我们以频率为基，所以这样看待傅立叶级数的方式就是“频域”。
>
> （注意基是函数，基坐标也是函数，而且基是无穷维的。指数形式的基和基坐标都是复数）
>
> 三角函数形式：
>
> <img src="Fourier.assets/image-20211011092132022.png" alt="image-20211011092132022" style="zoom:50%;" />



###### 连续傅里叶变换推导

> 黎曼积分图例：
>
> <img src="Fourier.assets/image-20211010165816580.png" alt="image-20211010165816580" style="zoom: 33%;" />

<img src="Fourier.assets/image-20211010104954081.png" alt="image-20211010104954081" style="zoom:50%;" />

($N$是周期，频率$w$等于$\frac{2\pi}{周期}$，$N\to +\infty$，$w$是‘基’频率(单位频率)，对应上式的$h$，$w_x$对应上式的$n\vdot h$)

(这里的公式7是任意函数的傅里叶变换。傅里叶积分定理，在周期$T$趋向于无穷的时候，这个周期函数会转化为任意一个我们需要的函数。)

<img src="Fourier.assets/image-20211010105231991.png" alt="image-20211010105231991" style="zoom:50%;" />

(上面$f(t)$是逆连续傅里叶变换，博主写错了)

($\displaystyle F\left(\omega_{x}\right)=\int_{t_{0}}^{t_{0}+T} f(t) e^{-i \omega_{x} t} dt = \displaystyle F\left(\omega_{x}\right)=\int_{-\frac{T}{2}}^{\frac{T}{2}} f(t) e^{-i \omega_{x} t} dt$，当$T\to +\infty$时，$\displaystyle F\left(\omega_{x}\right)=\int_{-\infty}^{+\infty} f(t) e^{-i \omega_{x} t} dt$(这个推导过程好像不对)，这个才是连续傅里叶变换)

(注意上面是不严格的推导，这里将黎曼积分的思想推广到无穷积分上)

<img src="Fourier.assets/image-20211010105315139.png" alt="image-20211010105315139" style="zoom:50%;" />

> *另一篇博客（无推导过程）：*
>
> <img src="Fourier.assets/image-20211011160132517.png" alt="image-20211011160132517" style="zoom: 67%;" />
>
> *wikipedia连续傅里叶变换的定义：*
>
> <img src="Fourier.assets/image-20211012114941017.png" alt="image-20211012114941017" style="zoom:50%;" />

> <img src="Fourier.assets/974efc6a99e06dcd623193e960ccbe93_1440w.jpg" alt="img" style="zoom:33%;" />
>
> <img src="Fourier.assets/097c9051af221c171730d4bc8f436a72_1440w.jpg" alt="img" style="zoom: 33%;" />

---

##### 离散傅里叶变换

[傅里叶系列（三）离散傅里叶变换（DFT） - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/75521342)

[如何通俗地解释什么是离散傅里叶变换？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/21314374)

（下面这个公式的$\displaystyle \int_{-\infty}^{+\infty}$是$\displaystyle \int_{t_0}^{t_0+T}$）

<img src="Fourier.assets/image-20211010171940394.png" alt="image-20211010171940394" style="zoom: 50%;" />

<img src="Fourier.assets/image-20211010172036242.png" alt="image-20211010172036242" style="zoom:50%;" />

（连续傅里叶变换公式中$N\to \infty$，这里$N$是采样点的个数）

（这里$\displaystyle \sum_{n=-\infty}^{+\infty}\int_{-\infty}^{+\infty}$变为$\displaystyle \sum_{n=0}^{N}$是因为在推导傅里叶级数指数形式时$\displaystyle \sum_{n=-\infty}^{+\infty}$是从$\displaystyle \sum_{n=0}^{+\infty}$推来的）

<img src="Fourier.assets/image-20211010172137723.png" alt="image-20211010172137723" style="zoom:50%;" />

$f(t)$得到一个复数一维设置，复数的模代表振幅，$\arctan(\frac{imag}{real})$代表相位

###### 线性代数角度看离散傅里叶变换

<img src="Fourier.assets/image-20211012112626159.png" alt="image-20211012112626159" style="zoom:50%;" />

<img src="Fourier.assets/v2-37ce5f225b2e6957476e519f72fef3d6_1440w.jpg" alt="img" style="zoom:50%;" />

> **wikipedia离散傅里叶变换的定义**
>
> <img src="Fourier.assets/image-20211012105035963.png" alt="image-20211012105035963" style="zoom:50%;" />

---

##### 快速傅里叶变换

<img src="Fourier.assets/image-20211012115842071.png" alt="image-20211012115842071" style="zoom: 50%;" />

---

##### 二维傅里叶变换

[图像傅里叶变换_Rachel Zhang的专栏-CSDN博客_傅里叶变换](https://blog.csdn.net/abcjennifer/article/details/7622228)

[傅里叶变换与图像的频域处理 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/54946461)

[二维傅里叶变换是怎么进行的？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/22611929)

<img src="Fourier.assets/image-20211012120618484.png" alt="image-20211012120618484" style="zoom:50%;" />

二维傅里叶变换是一维傅里叶变换在每一个行扫描线和列扫描线上的傅里叶变换的叠加

一维信号是一个序列，FT将其分解成若干个一维的简单函数之和。类比一维，**二维FT将一个图像分解成若干个复平面波** $e^{j2\pi(ux+vy)}$之和

<img src="Fourier.assets/image-20211013183029499.png" alt="image-20211013183029499" style="zoom: 50%;" />

从公式也可以看到，二维傅里叶变换就是将图像与每个**不同频率**的**不同方向**的复平面波做内积，也就是一个求在基**$e^{-j 2\pi(ux+vy)}$**上的投影的过程。

<img src="Fourier.assets/image-20211013165702393.png" alt="image-20211013165702393" style="zoom:50%;" />

傅里叶谱图上的每一个像素点都代表一个频率值，幅值由像素点亮度变码而得。最中心的亮点是指直流分量，傅里叶谱图中越亮的点，对应于灰度图中对比越强烈（对比度越大）的点。

由于每一列扫描线上没有变化，所以相应的fourier spectrum上行向量为0, 每一行扫描线上有contrast，所以有频率幅值。

<img src="Fourier.assets/image-20211013165931679.png" alt="image-20211013165931679" style="zoom:50%;" />

图像的频率是表征图像中灰度变化剧烈程度的指标，是灰度在平面空间上的梯度.在噪声点和图像边缘处的频率为高频。

傅立叶变换的物理意义是将图像的灰度分布函数变换为图像的频率分布函数，傅立叶逆变换是将图像的频率分布函数变换为灰度分布函数.

对图像进行二维傅立叶变换得到频谱图，就是图像梯度的分布图.

频谱图上的各点与图像上各点并不存在一一对应的关系，即使在不移频的情况下也是没有.

<img src="Fourier.assets/image-20211013170140302.png" alt="image-20211013170140302" style="zoom:50%;" />

###### 二维频率域K-SPACE

对于正弦平面波，可以这样理解，在一个方向上存在一个正弦函数，在法线方向上将其拉伸。三个参数可以确定一个一维的正弦波。

和一维的情况一样，频率$w$，幅度$A$，相位$\varphi$ ，再加一个方向 $\vec{n}$ 可以确定一个二维的正弦平面波

<img src="Fourier.assets/v2-259d7e69d3bf0aa454105bc97fe89073_1440w.jpg" alt="img"  />

类比一维中，幅度和相位可以用一个复数表示，它可以作为我们存储的内容，但是还有两个:一个频率，一个方向。这时想到向量是有方向的,也是有长度的，所以我们用一个二维的矩阵的来保存分解之后得到的信息，这个矩阵就是K空间

就是说一个二维矩阵点 $(u,v)$代表这个平面波的法向量 $\vec{n}$ ，这个向量的模$\sqrt{u^2+v^2}$代表这个平面波的频率$w$，这个点里面保存的内容复数就是此平面波的幅度(内容的模)和相位(内容的$\arctan(\frac{虚部}{实部})$)。

<img src="Fourier.assets/v2-73ad89919f066942a612107925152c8c_1440w.jpg" alt="img" style="zoom:67%;" />

eg. 8*8的基本余弦波

<img src="Fourier.assets/v2-f7dea0bc863cd9e4708268570306f3c6_1440w.jpg" alt="img" style="zoom:80%;" />



###### 图像的频域滤波

两个信号的乘积的傅里叶变换，等于它们各自的傅里叶变换的乘积。而在频域中两信号的乘积的反傅里叶变换等于它们各自的反傅里叶变换相卷积。

因此，可以通过在频域进行滤波，处理特定的频谱信号，再反傅里叶变换到空域来完成图像的滤波



<img src="Fourier.assets/v2-1cfcaf92cb50a5a5a6a14e82c31f5917_1440w.jpg" alt="img" style="zoom:50%;" />

---

##### 离散余弦变换

[详解离散余弦变换（DCT） - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/85299446)

在开始讲DCT变换之前，我们来看看DFT的变换公式

<img src="Fourier.assets/image-20211013192400910.png" alt="image-20211013192400910" style="zoom: 50%;" />

<img src="Fourier.assets/image-20211013192613695.png" alt="image-20211013192613695" style="zoom:50%;" />

<img src="Fourier.assets/image-20211013192705416.png" alt="image-20211013192705416" style="zoom:50%;" />

<img src="Fourier.assets/image-20211013195512925.png" alt="image-20211013195512925" style="zoom:50%;" />

<img src="Fourier.assets/image-20211013195923596.png" alt="image-20211013195923596" style="zoom:50%;" />

<img src="Fourier.assets/image-20211013200055017.png" alt="image-20211013200055017" style="zoom:50%;" />

<img src="Fourier.assets/image-20211013200325208.png" alt="image-20211013200325208" style="zoom:50%;" />

<img src="Fourier.assets/image-20211013200557408.png" alt="image-20211013200557408" style="zoom:50%;" />

