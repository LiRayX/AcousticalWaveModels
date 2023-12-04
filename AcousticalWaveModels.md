



# Acoustical Wave Models

## Ⅰ. Simplified Model and Layered Models

Ref : **Acoustical wave propagation in buried water filled pipes(2005)**. 

​		 **Fundamental Solutions in Elastodynamics**

​		 **The Foundations of Acoustics || The Wave Equation in Cylindrical Coordinates and Its Applications**

### 1.Simplified Model

#### i. Main idea

+ The pipe will be considered to be much stiffer than the water it contains, in which case the fluid is surrounded by a cylindrical boundary that allows no motions in the radial direction.(管道将被认为比其所容纳的水硬得多，在这种情况下，流体被圆柱形边界包围，不允许沿径向方向运动)

*Why we need this simplified model?*

*如果波可以穿过不止一种介质，特别是在固相和液相之间存在相互作用的情况下，在圆柱坐标系中严格制定声音传播是一个相当困难的问题*.(当然这种困难的问题在后面也有所讨论)

+ P波(primary wave or pressure wave,又称纵波 longitudinal wave, 疏密波 rarefaction waves),是指在传播介质中质点的振动方向与波的传播方向平行的一类波.
+ S波(secondary wave or shear wave,又称横波 transverse wave, 高低波 ), 横波是垂直于波的前进方向振动的波.

#### ii. Mathematical preliminaries and application

##### (1)Laplacian in cylindrical coordinates

圆柱坐标系下的拉普拉斯算子:
$$
\nabla^2 f = \frac {\part^2 f}{\part r^2}+\frac 1 r\frac{\part f}{\part r}+\frac{1}{r^2}\frac{\part^2 f}{\part \theta^2}+\frac{\part^2f}{\part z^2}
$$

~~上式只需利用chain rule即可,可以在任何一本数学分析/微积分的教材中找到,我们将在 wave equation 和 Helmholtz equation中多次使用它.~~[补充一下证明过程](#iii.-Laplacian)

##### (2)Bessel function

参考维基百科上的介绍: [Bessel function](https://zh.wikipedia.org/zh-hans/%E8%B4%9D%E5%A1%9E%E5%B0%94%E5%87%BD%E6%95%B0)

+ Bessel函数是Bessel方程的解

$$
x^2y''+xy'+(x^2-\alpha^2)y=0
$$

有三类贝塞尔函数,根据我们的需要进行选取即可.

+ Bessel函数的正交性:

由于贝塞尔方程对应的作用算符除以$x$后便是一个**自伴算子**(self-adjoint operator),所以它的解在适当边界条件下须满足正交性关系.特别地,有：
$$
\int_0^1 x J_\alpha\left(x u_{\alpha, m}\right) J_\alpha\left(x u_{\alpha, n}\right) d x=\frac{\delta_{m, n}}{2} J_{\alpha+1}\left(u_{\alpha, m}\right)^2
$$

##### (3)Acoustic wave equation

参考维基百科上的介绍: [Acoustic wave equation](https://en.wikipedia.org/wiki/Acoustic_wave_equation)

###### a. The form of solution

$$
\nabla^2 \phi = \frac{1}{c^2}\frac{\part^2\phi}{\part t^2}
$$

其中$c$是声速,$\phi$表示***abstract scalar field***,可以理解为***Velocity Potential***,

得到$\phi$后,$\bold{u} = \nabla\phi,p = -\rho \frac{\part\phi}{\part t} $.

利用(1)Laplacian in cyclindrical coordinates,得到:
$$
\frac{\partial^2 \phi}{\partial r^2}+\frac{1}{r} \frac{\partial \phi}{\partial r}+\frac{1}{r^2} \frac{\partial^2 \phi}{\partial \theta^2}+\frac{\partial^2 \phi}{\partial z^2}-\frac{1}{c^2} \frac{\partial^2 \phi}{\partial t^2}=0
$$
以上的[PDE的解](#iv.-Solution of the Wave Equation  in Cylindrical Coordinates)为:
$$
\phi(r, \theta, z)=\left(c_1 \cos (n \theta)+c_2 \sin (n \theta)\right) \cdot\left(c_3 J_n\left(k_a r\right)+c_4 Y_n\left(k_a r\right)\right) \cdot\left(c_5 e^{i k_z z}+c_6 e^{-i k_z z}\right)\text{ with }

k_a=\sqrt{k_p^2-k_z^2}
$$
根据物理模型的假设:波从波源向外移动$ \Rightarrow c_5 = 0$，并且在靠近波源的地方具有有限的强度$\Rightarrow c_4 = 0,\text{for } Y_n(x)\text{ explodes at $x=0$}$,解化简为:
$$
\phi(r, \theta, z)=\left(c_1 \cos (n \theta)+c_2 \sin (n \theta)\right) \cdot J_n\left(k_a r\right) \cdot e^{-i k_z z}
$$
根据Simplified Model中的假设,边界条件:
$$
u_r|_{r=R} = \frac{\partial\phi_{r}}{\partial r}|_{r=R} = 0 ,\text{ holds for }\forall \theta,z
$$
将此条件代入$\phi(r,\theta,z)$就得到:
$$
J_n^{\prime}\left(k_{n j} R\right)=0 \Leftrightarrow k_{n j} R=z_{n j}^{\prime} \Leftrightarrow k_{n j}=\frac{z_{n j}^{\prime}}{R}
$$

###### b. Solution of simplified model

以上的分析告诉了我们解具有的形式,现在考虑添加载荷项之后的方程的解.

+ 以$S(r,\theta,k_z,w)$表示波源的强度,并利用Fourier-Bessel级数(Fourier级数和Bessel级数的张量)展开:

$$
S\left(r, \theta, k_z, \omega\right)=\sum_{n=0}^{\infty} \sum_{j=1}^{\infty} S_{n j}=\sum_{n=0}^{\infty} \sum_{j=1}^{\infty}\left(a_{n j} \cos n \theta+b_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)
$$

其中,$k_{nj}:J_n'(k_{nj}R) = 0$

+ 由于Fourier-Bessel级数的正交性,Fourier系数可以由以下公式计算:

$$
\begin{aligned}
& a_{n j}=\frac{\int_0^R \int_0^{2 \pi} S(r, \theta, \omega) \cos m \theta J_m\left(k_{m i} r\right) r d r d \theta}{\frac{\pi}{2}\left(1+\delta_{0 n}\right) R^2 J_n^2\left(k_{n j} R\right)\left[1-\left(\frac{n}{k_{n j} R}\right)^2\right]} \text { for } n=0,1,2, \ldots \\
& b_{n j}=\frac{\int_0^R \int_0^{2 \pi} S\left(r, \theta, k_z, \omega\right) \sin m \theta J_m\left(k_{m i} r\right) r d r d \theta}{\frac{\pi}{2} R^2 J_n^2\left(k_{n j} R\right)\left[1-\left(\frac{n}{k_{n j} R}\right)^2\right]} \text { for } n>0
\end{aligned}
$$

+ 添加载荷项之后的方程为:


$$
\begin{aligned}
&\nabla^2 \phi+k^2 \phi=\sum_{n=0}^{\infty} \sum_{j=1}^{\infty}\left(a_{n j} \cos n \theta+b_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)\\
&k^2=k_0^2-k_z^2 \text { and } k_0=\omega / c \text {. }
\end{aligned}
$$

+ 为了求解以上的方程,考虑$\phi$的Fourier-Bessel展开(注意,此时考虑的$\phi$是频域$k_z,w$上的函数):

$$
\phi\left(r, \theta, k_z, \omega\right)=\sum_{n=0}^{\infty} \sum_{j=1}^{\infty} \phi_{n j}=\sum_{n=0}^{\infty} \sum_{j=1}^{\infty}\left(A_{n j} \cos n \theta+B_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)
$$

+ 代入添加了载荷项之后的方程,有:

$$
\sum_{n=0}^{\infty} \sum_{j=1}^{\infty}\left(\nabla^2+k^2\right)\left(A_{n j} \cos n \theta+B_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)=\sum_{n=0}^{\infty} \sum_{j=1}^{\infty}\left(a_{n j} \cos n \theta+b_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)
$$

+ 由线性无关性:

$$
\left(\nabla^2+k^2\right)\left(A_{n j} \cos n \theta+B_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)=\left(a_{n j} \cos n \theta+b_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)
$$



​		整理后得到:
$$
\left\{\left[\left(J_n^{\prime \prime}+\frac{1}{r} J_n^{\prime}+\left(k_{n j}^2-\left(\frac{n}{r}\right)^2\right) J_n\right)\right]+\left(k^2-k_{n j}^2\right) J_n\right\}\left(A_{n j} \cos n \theta+B_{n j} \sin n \theta\right)=\left(a_{n j} \cos n \theta+b_{n j} \sin n \theta\right) J_n
$$
​		注意到$J_n''+\frac1rJ_n'+(k_{nj}^2-(\frac{n}{r})^2J_n$即为Bessel方程的左端项,从而为0;

+ 解得

$$
\begin{aligned}
k^2-k_{n j}^2&=k_0^2-k_{n j}^2-k_z^2,\\
A_{n j}=\frac{-a_{n j}}{\left(k_z-\sqrt{k_0^2-k_{n j}^2}\right)\left(k_z+\sqrt{k_0^2-k_{n j}^2}\right)}& \text { and } B_{n j}=\frac{-b_{n j}}{\left(k_z-\sqrt{k_0^2-k_{n j}^2}\right)\left(k_z+\sqrt{k_0^2-k_{n j}^2}\right)}
\end{aligned}
$$

+ 以上的$A_{nj},B_{nj}$是$\phi$中所有包含轴向波数$k_z$的项,进行Fourier逆变换:

$$
I_j=\frac{1}{2 \pi} \int_{-\infty}^{+\infty} \frac{e^{-\mathrm{i} k_z z} d k_z}{\left(k_z-\sqrt{k_0^2-k_{n j}^2}\right)\left(k_z+\sqrt{k_0^2-k_{n j}^2}\right)}
$$

​	此积分可以由留数定理(积分区域取$R\rightarrow-R(Re^{i\pi})\stackrel{cycle}{\longrightarrow}Re^{i2\pi}$)计算:
$$
I_j=-2 \pi \mathrm{i} \frac{1}{2 \pi} \frac{e^{-\mathrm{i} z \sqrt{k_0^2-k_{n j}^2}}}{2 \sqrt{k_0^2-k_{n j}^2}}=-\frac{\mathrm{i} e^{-\mathrm{i} z \sqrt{k_0^2-k_{n j}^2}}}{2 \sqrt{k_0^2-k_{n j}^2}}
$$

+ 最终得到的解为:

$$
\phi(r, \theta, z, \omega)=\frac{\mathrm{i}}{2} \sum_{n=0}^{\infty} \sum_{j=1}^{\infty} \frac{e^{-\mathrm{i} z \sqrt{k_0^2-k_{n j}^2}}}{\sqrt{k_0^2-k_{n j}^2}}\left(a_{n j} \cos n \theta+b_{n j} \sin n \theta\right) J_n\left(k_{n j} r\right)
$$

现在我们只需要求出$S(r,\theta,k_z,w)$中的对应系数$a_{nj},b_{nj},k_{nj}$即可,接下来我们来确定这件事.

##### (4)Specific form of the solution

###### a. off-center point source

+ 假设波源偏离中心的距离为$a$,如下图所示:

<img src=".\AcousticalWaveModels.assets\image-20231120102630687.png" alt="image-20231120102630687" style="zoom:80%;" />

+ 波源的强度函数表达为:

$$
S(r,\theta,z,w) = \frac 1r\delta(r-a)\delta(\theta)\delta(z)f(w)
$$

​	注意,这是一个频域$(w)$上的函数,$\delta(\cdot)$表示[狄拉克函数](https://zh.wikipedia.org/zh-hans/%E7%8B%84%E6%8B%89%E5%85%8B%CE%B4%E5%87%BD%E6%95%B0),它是一个分布函数,可以用标准正态分布方差趋于$0$的序列的弱极限来表示.狄拉克函数在信号处理上也被称为**单位脉冲符号**或**单位脉冲函数**.

​	以上的表达式是为了说明我们在某个点发出了信号.

+ 波源的强度满足以下表达式:

$$
\int_0^R \int_0^{2 \pi} S\left(r, \theta, k_z, \omega\right) r d r d \theta=\delta(z) f(\omega)
$$

+ 我们计算出对应的$a_{nj},b_{nj}$:

$$
a_{n j}=\frac{J_n\left(k_{n j} a\right)}{\frac{\pi}{2}\left(1+\delta_{0 n}\right) R^2 J_n^2\left(k_{n j} R\right)\left[1-\left(\frac{n}{k_{n j} R}\right)^2\right]}, b_{n j}=0
$$

+ 最终得到$\phi$的表达式

$$
\phi(r, \theta, z, \omega)=\frac{\mathrm{i}}{\pi R^2} f(\omega) e^{\mathrm{i} \omega x} \sum_{n=0}^{\infty} \sum_{j=1}^{\infty} \frac{e^{-\mathrm{i} z \sqrt{k_0^2-k_{n j}^2}}}{\sqrt{k_0^2-k_{n j}^2}} \frac{\cos n \theta J_n\left(k_{n j} a\right) J_n\left(k_{n j} r\right)}{\left(1+\delta_{0 n}\right) J_n^2\left(k_{n j} R\right)\left[1-\left(\frac{n}{k_{n j} R}\right)^2\right]}
$$

以上的计算需要在很大的范围内进行双重求和,代价比较昂贵.

###### b. center point source

+ $a=0$时,波源的强度函数表达为:

$$
S(r,\theta,z,w) = \frac 1r\delta(r)\delta(\theta)\delta(z)f(w)
$$

+ 此时非零的系数仅有:

$$
a_{0 j}=\frac{1}{\pi R^2 J_0^2\left(k_{0 j} R\right)}, a_{n>0, j}=0, b_{n j}=0
$$

+ $\phi$的表达式(频域)

$$
\phi(r, \theta, z, \omega)=\frac{\mathrm{i}}{2 \pi R^2} f(\omega) e^{\mathrm{i} \omega x} \sum_{j=1}^{\infty} \frac{e^{-\mathrm{i} z \sqrt{k_0^2-k_0^2, j}}}{\sqrt{k_0^2-k_{0 j}^2}} \frac{J_0\left(k_{0 j} r\right)}{J_0^2\left(k_{0 j} R\right)}
$$

+ $p=\rho \frac{\part\phi}{\part t}$的表达式(频域)

$$
p(r, \theta, z, \omega)=\frac{\rho}{c R^2} \omega f(\omega) e^{\mathrm{i} \omega x} \sum_{j=1}^{\infty} \frac{e^{-\mathrm{i} z \sqrt{k_0^2-k_{0 j}^2}}}{\sqrt{k_0^2-k_{0 j}^2}} \frac{J_0\left(k_{0 j} r\right)}{J_0^2\left(k_{0 j} R\right)}
$$

​	对于以上的表达式,注意到管道的normal modes为:$k_{0j} = w_{0j}/c=z_{0j}/R$,即
$$
\omega_{n j}=z_{n j} \frac{c}{R} \rightarrow k_{n j} r=z_{n j} \frac{r}{R}, k_{n j} a=z_{n j} \frac{a}{R} \text { with } J_n^{\prime}\left(z_{n j}\right)=0
$$

#### iii. Algorithm

维基百科:[短时距傅里叶变换](https://zh.wikipedia.org/zh-hans/%E7%9F%AD%E6%99%82%E8%B7%9D%E5%82%85%E7%AB%8B%E8%91%89%E8%AE%8A%E6%8F%9B)

##### (1)Exponential Window Method

###### a. EWM数学原理

1. Given a displacement (or any other variable) of the form:

$$
u(t) = \frac 1 {2\pi}\int_{-\infty}^{+\infty}F(w)H(w)e^{iwt}dw
$$

2. if one adds an artificial damping to the frequency, this integral can be evaluated by contour integration as:

$$
u(t) = \frac 1 {2\pi}\int_{-\infty}^{+\infty}F(w-i\eta)H(w-i\eta)e^{i(w-i\eta)t}dw = \frac{1}{2\pi}e^{\eta t}\int_{-\infty}^{+\infty}F(w-i\eta)H(w-i\eta)e^{iwt}dw = e^{\eta t}\overline{u}(t)
$$

​		with
$$
F(w-i\eta) = \int_0^{t_0}(e^{-\eta t}f(t))e^{-iwt}dt = \int_0^{t_0}\overline{f}(t)e^{-iwt}dt
$$

###### b. EWM流程图

图中的$w$参考[如何计算$w$](#(4)-w-in-DFT)

![image-20231119124640936](.\AcousticalWaveModels.assets\image-20231119124640936.png)



###### c. EWM算法流程

***One. Acoustical wave propagation in buried water filled pipes*** 

+ Calculate the FFT of the forcing function
+ Multiply it by a falling exponential window
+ Calculate the transfer function for the complex frequency
+ Multiply the FFT of the forcing function and the transfer function to get the response function
+ Do the inverse FFT
+ Multiply the resulting displacement by a rising exponential window with the same parameter $\eta$ to get the actual response

$EWM:\text{force function }f(t)\stackrel{FEW}{\longrightarrow}e^{-\eta t}f(t)\stackrel{FFT}{\longrightarrow}F(\overline{w})\xrightarrow[multiply]{calculate H(w)}\phi^*(r,\theta,z,\overline{w})\stackrel{IFFT}{\longrightarrow}\phi^*(r,\theta,z,t)\stackrel{REW}{\longrightarrow}\phi(r,\theta,z,t)$

***Two. Frequency domain analysis by the exponential window method and SGBEM for elastodynamics***

原文中对于EWM方法的介绍缺少了一些细节,参考了以上的论文中的过程:

1. 确定频率分辨率$\Delta f$,应当足够小以尽量减少频率信息的损失
2. 确定exponential window function中的shifting constant $\eta$, 公式:  $\eta = m_0\Delta f\ln10, 3\leq m_0 \leq 4 \;\text{is recommended} $
3. *对一系列 (N /2 + 1) 位移角频率进行 SGBEM(Symmetric-Galerkin Boundary Element Method)分析:*
   + $\overline{w_j}=2\pi(j\Delta f)-i\eta,\;j=0:N/2)$得到前$N/2+1$个样本的 scaled frequency response $G(\overline{w})$;其中$N=2^m$, $m$是与Nyquist frequency $f_{Nyq} = \frac N2\Delta f=2^{(m-1)}\Delta f $.该频率需要足够大,意味着高于 $f_{Nyq}$ 的频率响应并不重要,可以被丢弃.请注意,第一个样本 $(j = 0)$ 对应于静态样本.
4. *对于最后的$N/2-1$个样本,$G(\overline{w})$关于Nyquist frequency共轭对称:*
   + $G(\overline{w_j}) = \text{conj}(G(\overline{w}_{N-j+2}),\;j=N/2+2:N)$
5. 对于scaled loading function $\hat{P}(t) = e^{-\eta t}P(t)$的前$N(j=1:N)$个样本执行FFT,得到
   + $P(\overline{w}) = \int_0^{T_f}\hat{P}(t)e^{-iwt}dt,\;T_f = 1/\Delta f$
6. 计算scaled output$X(\overline{w}) = G(\overline{w})Y(\overline{w})$
7. 对$X(\overline{w})$执行IFFT,得到scaled time response:
   + $\hat{X}(t) = \frac 1{2\pi}\int_{-\infty}^{+\infty}X(\overline{w})e^{i\overline{w}t}dw$
8. 真正的时间响应为$X(t) =e^{\eta t}\hat{X}(t)$,时间分辨率为$\Delta t = T_f/N$;
9. 如果计算出的$\Delta t$不能很好地指示time-history曲线的形状,可以考虑进行插值(**Ref**: ***Brigham EO (1988) The fast Fourier transform and its applications. Prentice Hall, New Jersey***).

+ 以上的流程中,$3,4$中的SGBEM数值技术适合 $G(\overline{w})$ 是动态应力强度因子 (DSIF) 或动态T应力等裂缝参数的scaled frequency response.
  + *This numerical technique is particularly suitable if  $G(\overline{w})$ is the scaled frequency response for fracture parameters such as the dynamic stress intensity factors (DSIFs) or the dynamic T -stress*

##### (2)Algorithm for simplified model

After these brief notes on the EWM application the layout of the numerical code that calculates the response to an impact excitation will be:

1. Defining the forcing function

2. Choosing the distance for which the response is calculated
3. Choosing the timeframe under which the system is studied
4. Deciding on the number of discretization points
5. Calculating the Nyquist frequency for the FFT
6. Discretizing the frequency domain
7. Calculating the forcing function strength at all the discretization points
8. Calculating the FFT of forcing function
9. Choosing a value of damping for the EWM
10. Calculating the EW function
11. Multiplying the EW with the FFT of the forcing function
12. Choosing the appropriate number of modes (value of n) and of terms of the Bessel-Fourier series (value of j)

13. Calculating the response for all the frequencies (transfer function)
14. Multiplying the transfer function with the FFT of the forcing function
15. Executing an IFFT to calculate the response of the system in time
16. Multiplying the response with the inverse EW
17. Doing the above analysis for a range of distances

**Notes**： 

+ 实际上,只有少数离散时间点会给出非零的 foring function,但增加零是执行 FFT 所必需的.

+ 为了计算贝塞尔-傅立叶级数所有项的响应，需要贝塞尔函数一阶导数的根.作者使用了单独的代码来计算根:该代码基于二分法.

+ Nyquist criterion: FFT分析的最大频率必须至少比force function的主频率高2倍.

+ 时域中的力必须使用至少6个点进行离散化,才能相对准确地表达力函数.

**Result**:

以5ms的脉冲为例

<img src=".\AcousticalWaveModels.assets\image-20231119160142473.png" alt="image-20231119160142473" style="zoom: 80%;" />

![templatepulse](.\AcousticalWaveModels.assets\templatepulse.png)

+ **The theoretical time it takes for sound to travel z is $0.06666666666666667$(s) and it is already marked on the diagram with a red dotted line**

![pressure_response](.\AcousticalWaveModels.assets\pressure_response.png)

![FrequencyDomain](.\AcousticalWaveModels.assets\FrequencyDomain.png)

### 2.Layered Models

从**Chapter6(Page 55)**,开始讨论由若干个同心圆柱层组成的系统:

+ Single layer(最外层是孤立的自由层,单层外半径和内半径分别为$r_1,r_2$)
+ Unbounded external region(外部被视为无限大的层)
+ Layered system(多层系统,可以是无界的外部区域)

我们所需要的流体-管道-土壤模型(下图,Page 64 of thesis),属于case 2: Unbounded external region.

<img src=".\AcousticalWaveModels.assets\image-20231119204312007.png" alt="image-20231119204312007" style="zoom:50%;" />

#### i. Main idea

+ 考虑一个由$N - 1$个任意厚度的同心圆柱层组成的系统，我们从外到内对这$N$个界面进行编号.可选择无限大的外部区域可以围绕这些层.将假定每层中的材料特性与方位角$\theta$无关并且在每个圆柱形层内是均匀的。

#### ii. Mathematical preliminaries

##### (1)General case

***As shown by Kausel [Compendium of Fundamental Solutions in Elastodynamics, Cambridge University Press, in print],***

+ 给定轴向波数$k_z$和频率$w$,单个圆柱层内部某点位移矢量的特定解具有以下形式

$$
\begin{gathered}
\overline{\mathbf{u}}(r, \theta, z, \omega)=\left[\begin{array}{lll}
\bar{u}_r & \bar{u}_\theta & -\mathrm{i} \bar{u}_z
\end{array}\right]^T=\mathbf{T}_n\left(\mathbf{H}_n^{(1)} \mathbf{a}_1+\mathbf{H}_n^{(2)} \mathbf{a}_2\right) e^{-\mathrm{i} k_z z} \equiv \mathbf{T}_n \mathfrak{u} e^{-\mathrm{i} k_z z} \\
\mathfrak{u}=\mathfrak{u}\left(r, k_z, \omega\right)=\left[\begin{array}{lll}
\tilde{u}_r & \tilde{u}_\theta & -\mathrm{i} \tilde{u}_z
\end{array}\right]^T=\mathbf{H}_n^{(1)} \mathbf{a}_1+\mathbf{H}_n^{(2)} \mathbf{a}_2
\end{gathered}
$$

+ 圆柱表面上的应力

$$
\begin{aligned}
& {\left[\begin{array}{lll}
\bar{\sigma}_r & \bar{\sigma}_{r \theta} & -\mathrm{i} \bar{\sigma}_{r z}
\end{array}\right]^T=\mathbf{T}_n\left(\mathbf{F}_n^{(1)} \mathbf{c}_1+\mathbf{F}_n^{(2)} \mathbf{c}_2\right) e^{-\mathrm{i} k_z z}=\mathbf{T}_n \mathfrak{s} e^{-\mathrm{i} k_z z}} \\
& \mathfrak{s}=\mathfrak{s}(r)=\left[\begin{array}{lll}
\tilde{\sigma}_r & \tilde{\sigma}_{r \theta} & -\mathrm{i} \tilde{\sigma}_{r z}
\end{array}\right]^T=\mathbf{F}_n^{(1)} \mathbf{a}_1+\mathbf{F}_n^{(2)} \mathbf{a}_2
\end{aligned}
$$

##### (2)Layered Models

###### a. Single layer

最外层是孤立的自由层,单层外半径和内半径分别为$r_1,r_2$,分别计算这两个表面上的位移和应力,得到：
$$
\left\{\begin{array}{l}
\mathfrak{u}_1 \\
\mathfrak{u}_2
\end{array}\right\}=\left\{\begin{array}{ll}
\mathbf{H}_{n 1}^{(1)} & \mathbf{H}_{n 1}^{(2)} \\
\mathbf{H}_{n 2}^{(1)} & \mathbf{H}_{n 2}^{(2)}
\end{array}\right\}\left\{\begin{array}{l}
\mathbf{a}_1 \\
\mathbf{a}_2
\end{array}\right\}, \quad\left\{\begin{array}{l}
\mathfrak{p}_1 \\
\mathfrak{p}_2
\end{array}\right\}=\left\{\begin{array}{r}
r_1 \mathfrak{s}_1 \\
-r_2 \mathfrak{s}_2
\end{array}\right\}=\left\{\begin{array}{cc}
r_1 \mathbf{F}_{n 1}^{(1)} & r_1 \mathbf{F}_{n 1}^{(2)} \\
-r_2 \mathbf{F}_{n 2}^{(1)} & -r_2 \mathbf{F}_{n 2}^{(2)}
\end{array}\right\}\left\{\begin{array}{l}
\mathbf{a}_1 \\
\mathbf{a}_2
\end{array}\right\}
$$
其中下标表示计算矩阵的位置,上标表示使用的Bessel函数的类型.

+ 消去$a_1,a_2$

$$
\begin{aligned}
\left\{\begin{array}{l}
\mathfrak{p}_1 \\
\mathfrak{p}_2
\end{array}\right\} & =\left\{\begin{array}{cc}
r_1 \mathbf{F}_{n 1}^{(1)} & r_1 \mathbf{F}_{n 1}^{(2)} \\
-r_2 \mathbf{F}_{n 2}^{(1)} & -r_2 \mathbf{F}_{n 2}^{(2)}
\end{array}\right\}\left\{\begin{array}{ll}
\mathbf{H}_{n 1}^{(1)} & \mathbf{H}_{n 1}^{(2)} \\
\mathbf{H}_{n 2}^{(1)} & \mathbf{H}_{n 2}^{(2)}
\end{array}\right\}^{-1}\left\{\begin{array}{l}
\mathfrak{u}_1 \\
\mathfrak{u}_2
\end{array}\right\} 
 =\left\{\begin{array}{l}
\mathbf{K}_{11} \mathbf{K}_{12} \\
\mathbf{K}_{21} \mathbf{K}_{22}
\end{array}\right\}\left\{\begin{array}{l}
\mathfrak{u}_1 \\
\mathfrak{u}_2
\end{array}\right\}
\end{aligned}
$$

​	$K$称作刚度矩阵:
$$
\mathbf{K}=\left\{\begin{array}{ll}
\mathbf{K}_{11} & \mathbf{K}_{12} \\
\mathbf{K}_{21} & \mathbf{K}_{22}
\end{array}\right\}=\left\{\begin{array}{cc}
r_1 \mathbf{F}_{n 1}^{(1)} & r_1 \mathbf{F}_{n 1}^{(2)} \\
-r_2 \mathbf{F}_{n 2}^{(1)} & -r_2 \mathbf{F}_{n 2}^{(2)}
\end{array}\right\}\left\{\begin{array}{cc}
\mathbf{H}_{n 1}^{(1)} & \mathbf{H}_{n 1}^{(2)} \\
\mathbf{H}_{n 2}^{(1)} & \mathbf{H}_{n 2}^{(2)}
\end{array}\right\}^{-1}
$$

###### b. Unbounded external region

对于无界均匀空间内的圆柱形空腔,外部区域可以被视为外半径无限大的层.在这种情况下,$a_2$ 必定为零.因此,外部区域的 $3\times3$ 刚度矩阵:
$$
K_{ext} = -rF_n^{(2)}(H_n^{(2)})^{-1}
$$
###### c. Layered system

从外部区域的刚度矩阵开始,为每一层创建层矩阵,得到以下的分块三对角阵:
$$
\begin{pmatrix}
p_1\\
p_2\\
p_3\\
\vdots\\
p_N
\end{pmatrix}
=
\begin{pmatrix}
K_{11} & K_{12} & 0 & \cdots & 0 \\
K_{21} & K_{22} & K_{23} & \cdots & 0 \\
0 & K_{32} & K_{33} & \ddots & \vdots \\
\vdots & \vdots & \ddots & \ddots & K_{N-1,N} \\
0 & 0 & \cdots & K_{N,N-1} & K_{NN}  \\
\end{pmatrix}
\begin{pmatrix}
u_1\\
u_2\\
u_3\\
\vdots\\
u_N
\end{pmatrix}
$$

<img src=".\AcousticalWaveModels.assets\image-20231130220457504.png" alt="image-20231130220457504" style="zoom:80%;" />



###### d. Solid core

$$
K_{core} = rF_nH_n^{-1}
$$

以上的刚度矩阵,利用$J_n$计算.

##### (3)Fluid-pipes-soil model

###### a. step 1

波源在layered medium中引起$r_N$处的位移和内部压力分别为$u_N,s_n$

波源在同质的无限介质中引起$r_N$处的位移和内部压力分别为$u^*,s^*$
$$
r_N(s_N-s^*) = K_{core}(u_N - u ^*),\text{with} \: K_{core} = r_NF_N(H_N)^{-1}
$$
此外,由于外部区域没有波源,因此齐次参考问题的应力满足平衡条件
$$
-r_Ns^* = K_{ext}u^*\quad K_{ext} = -r_N F_N^{(2)}(H_N^{(2)})^{-1}
$$
化简得到:
$$
-r_N s_N = - K_{core}u_N + K_{full}^*u^* \quad K_{full}^* = K_{core} + K_{ext}^*
$$
写成矩阵的形式:
$$
\begin{pmatrix}
K_{11} & K_{12} & 0 & \cdots & 0 \\
K_{21} & K_{22} & K_{23} & \cdots & 0 \\
0 & K_{32} & K_{33} & \ddots & \vdots \\
\vdots & \vdots & \ddots & \ddots & K_{N-1,N} \\
0 & 0 & \cdots & K_{N,N-1} & K_{NN} + K_{core} \\
\end{pmatrix}
\begin{pmatrix}
u_1\\
u_2\\
u_3\\
\vdots\\
u_N
\end{pmatrix}
= 
\begin{pmatrix}
0\\
0\\
0\\
\vdots\\
K_{full}^* u^*
\end{pmatrix}
$$

现在,只需要求出$u^*$即可.

以上的刚度矩阵,见[Table 1](#(1)-Table-1) [Table 2](#(2)-Table-2)

###### b. step 2

柱坐标系下的[Green's functions](https://zh.wikipedia.org/wiki/%E6%A0%BC%E6%9E%97%E5%87%BD%E6%95%B8)

Let $g_j (r, r') = g_j (r, r', t)$ or $g_j (r, r') = g_j (r, r', w)$ be the Green’s function for a receiver placed at location $r$ due to an impulsive or harmonic source, a point load $P = 1$ acting at location $r'$ in some principal direction $j$.

+  When the Green’s functions for a point load acting on the cylindrical axis (i.e.,$ r' = 0$) at depth $z'$ are expressed in cylindrical coordinates, they have the general form

$$
\begin{aligned}
& u=A\left(k_{\mathrm{S}}^2 H_{0 \beta}-\frac{1}{r} B_1+B_2\right), \\
& v=A\left(k_S^2 H_{0 \beta}-\frac{1}{r} B_1\right) \\
& w=A \mathrm{i} k_z B_1, \\
& U=A \mathrm{i} k_z B_1 \\
& W=A\left(k_{\mathrm{S}}^2 H_{0 \beta}-k_z^2 B_0\right)
\end{aligned}
$$

The radial, tangential, and axial components of the Green's functions are then
$$
\begin{aligned}
&g_{r x}=u(\cos \theta),\quad g_{r y}=u(\sin \theta), \;g_{r z}=U \\
&g_{\theta x}=v(-\sin \theta),\;g_{\theta y}=v(\cos \theta), \;g_{\theta z}=0 \\
&g_{z x}=w(\cos \theta), \quad g_{z y}=w(\sin \theta),\;g_{z z}=W \\
\end{aligned}
$$
以上涉及到的字母,参考[Table 3](#(3)-Table-3)

其中,$g_{ij}$表示$j$方向的单位载荷对于$i$方向的影响.

如果求和$\bold{g_{j}} = g_i^je^{i}$($g_i^j = g_{ij}$)则表示$j$方向的单位载荷对于所有方向的影响,在三维空间中,$\bold{g_j}$是个三维列向量.

(通常,我们以$\bold{i},\bold{j},\bold{k}$表示Cartesian coordinates下的标准正交基,$\bold{r},\bold{t},\bold{k}$表示柱面坐标系的标准正交基)
$$
\begin{array}{ll}
\mathbf{g}_z=U\left(r, z, z^{\prime}\right) \hat{\mathbf{r}}+W\left(r, z, z^{\prime}\right) \hat{\mathbf{k}} & \text { Vertical z load } \\
\mathbf{g}_x=u\left(r, z, z^{\prime}\right) \cos \theta \hat{\mathbf{r}}+v\left(r, z, z^{\prime}\right)(-\sin \theta) \hat{\mathbf{t}}+w\left(r, z, z^{\prime}\right) \cos \theta \hat{\mathbf{k}} & \text { Horizontal x load } \\
\mathbf{g}_y=u\left(r, z, z^{\prime}\right) \sin \theta \hat{\mathbf{r}}+v\left(r, z, z^{\prime}\right) \cos \theta \hat{\mathbf{t}}+w\left(r, z, z^{\prime}\right) \sin \theta \hat{\mathbf{k}} & \text { Horizontal y load }
\end{array}
$$
$ u =\sum \bold{g_x}$

声波在液体中只有P波于是只需要考虑$\bold{g_z}$即可.

###### c . Result

<img src=".\AcousticalWaveModels.assets\image-20231120135142828.png" alt="image-20231120135142828" style="zoom:80%;" />

#### iii. Algorithm

我们根据以下参数来选择需要的模型,具体的算法步骤参考1.Simplified Model,其中的 $L$ 是所考虑的最大频率与信号“频率”(持续时间的倒数)的比率,$\xi$表示damping ratio.

<img src=".\AcousticalWaveModels.assets\image-20231119163700365.png" alt="image-20231119163700365" style="zoom:80%;" />

### 3. Appendix

#### i. DFT&FFT

***为了方便,以下所有的下标从零开始.***

##### (1) Orthogonal basis

对于内积空间$(\C^N,(\cdot,\cdot))$,其中内积为标准内积$(x,y) = x'\overline{y} = \sum_{j=0}^{N-1}x_j\overline{y_j}$,

 $\{e_k = (e^{iwk \cdot 0},e^{iwk \cdot 1},...,e^{iwk \cdot(N-1)})\}_{k=0}^{N-1}, \;w = \frac{2\pi}{N}$构成了一组正交基:

*Proof:* 记$w_1 = e^{iw} = e^{i\frac{2\pi}{N}}$为$1$的$N$次方根.

+ $(e_k,e_l) = \sum_{j=0}^{N-1} w_1^{kj}w_1^{-lj} = \sum_{j=0}^{N-1}w_1^{j(k-l)} $

+ 如果$k=l$,$(e_k,e_l) = \sum_j 1 = N$

+ 如果$k\neq l$,$(e_k,e_l) = \sum_{j} (w_1^{k-l})^j = 0$ ,这可在$1+z+z^2+\cdots+z^{N-1} = \frac{Z^N-1}{z-1}$中,令$z = w_1^{k-l}$得到.

##### (2) DFT

从而对于一个向量$x = (x_0,x_1,...,x_{N-1})' = \sum_k c_k e_k$, 此时$c_j$即为Fourier系数

+ $X[k] = c_k = \frac{(x,e_k)}{(e_k,e_k)} = \frac1N\sum_j x_j e^{-iwk\cdot j}$

如果写成矩阵的形式:($w_{N-1} = \overline{w}_1 = e^{iw(N-1)} $)
$$
F  = 
\begin{pmatrix}
1 & 1 & 1 & \cdots &1 \\
1 & w_{N-1}^1 &w_{N-1}^2 &\cdots &w_{N-1}^{N-1} \\
\vdots & \vdots &\vdots &\ddots &\vdots \\
1 &w_{N-1}^{N-1} &w^{2(N-1)}&\cdots & w_{N-1}^{(N-1)(N-1)}
\end{pmatrix}
$$

+ $X = (X[0],X[1],...,X[N-1])' = \frac1N F x$
+ 注意到$FF^{H} = N I_{NN}$,从而**IDFT**也不难得到.

##### (3) FFT

假设$N = p^{m}$其中$p$是个素数,特别地,对于$p = 2$的情况:

按照模$2$的余数,将$F = (f_0,f_1,...,f_{N-1})$的列分为两类:

+ $\tilde{F} = FP = (f_0,f_2,...,f_{N-2},f_1,f_3,...,f_{N-1})$其中$P$为排列矩阵.
+ 将$\tilde{F}$分为四块,$\tilde{F} = \begin{pmatrix} F_{1} & F_2\\ F_3 &F_4 \end{pmatrix}$,每一块的大小均为$\frac N2 \times \frac{N}{2}$
+ 注意到$w_{N-1}^{N} = 1,\text{ yields } F_3 = F_1$
+ $F_2 = \Omega F_1$,其中$\Omega = \text{diag}\{1,w_{N-1}^1,\cdots,w_{N-1}^{N/2}\}$
+ $F_4 = \Omega_*F_3 $,其中$\Omega_* = \text{diag}\{w_{N-1}^{N/2+1},w_{N-1}^{N/2+2},\cdots,w_{N-1}^{N-1}\} = -\Omega$

$Fx = FPPx = \tilde{F}\tilde{x} = \begin{pmatrix} I & \Omega\\ I & -\Omega \end{pmatrix}\begin{pmatrix} F_1x[0:2:end] \\ F_1x[1:2:end]  \end{pmatrix}$

由(2)中的论证,**IFFT**同理.

##### (4) w in DFT

对于一段长度为$T$秒的音频,采样率为$f_s$,此时得到了向量的长度为$N = T\cdot f_s$

此时,傅里叶变换中对应的$w$应该是什么?

对于信号:

| $t/\frac{1}{f_s}$ |  $0$   |  $1$   | $\cdots$ |  $N-1$   |
| :---------------: | :----: | :----: | :------: | :------: |
|      $f(t)$       | $x[0]$ | $x[1]$ | $\cdots$ | $x[N-1]$ |

经过FFT之后得到:

| $F(w)$ | $X[0]$ | $X[1]$ | $\cdots$ | $X[N-1]$ |
| :----: | :----: | :----: | :------: | :------: |

+ 以$t=(t_0,t_1,...,t_{N-1})'$表示时间序列,从而$ t_j = j/f_s$
+ $x = \sum_k X[k]e_k$,其中$e_k$是$e^{i\frac{2\pi}{N}k}$生成的,

$$
\begin{aligned}
f(t_j) = f(\frac jf_s) = x_j &= \sum_kX[k]w_1^{j\cdot k}\\ 
&= \sum_k X[k]e^{i\frac{2\pi}{N}j\cdot k}\\
&= \sum_k X[k]e^{i\frac{2\pi}{N}f_st_j\cdot k}\\
&= \sum_k X[k]e^{iw_kt_j}\\
\end{aligned}
$$

+ 即$w_k = \frac{2\pi}{N}f_s k = \frac{2\pi}{T}k,\quad k=0,1,...,N-1$

#### ii. Table

##### (1) Table 1

<img src=".\AcousticalWaveModels.assets\image-20231201125248157.png" alt="image-20231201125248157" style="zoom:80%;" />

##### (2) Table 2

<img src=".\AcousticalWaveModels.assets\image-20231201125420334.png" alt="image-20231201125420334" style="zoom:80%;" />

##### (3) Table 3


$$
\begin{array}{ll}
A=\frac{1}{4 \mathrm{i} \rho \omega^2} & \text { Amplitude } \\
r=\sqrt{x^2+y^2} \equiv \sqrt{x_1^2+x_2^2} & \text { Source-receiver distance } \\
\gamma_i=\frac{\partial r}{\partial x_i}=\frac{x_i}{r}, \quad i=1,2 & \begin{array}{l}
\text { Direction cosines in the } x, y \\
\text { plane }
\end{array} \\
\delta_{i i}=\delta_{11}+\delta_{22}=2, \quad \gamma_i \gamma_i=\gamma_1^2+\gamma_2^2=1 & \text { Implied summations } \\
\gamma_{i, j}=\frac{1}{r}\left(\delta_{i j}-\gamma_i \gamma_j\right) & \text { First derivatives of } \gamma_i, i, j=1,2\\
\gamma_{i, j k}=\frac{1}{r^2}\left(3 \gamma_i \gamma_j \gamma_k-\gamma_i \delta_{j k}-\gamma_j \delta_{k i}-\gamma_k \delta_{i j}\right) & \text { Second derivatives } \\
k_z & \text { Wavenumber in } z \text { direction } \\
k_{\mathrm{P}}=\frac{\omega}{\alpha} & \text { Wavenumber for P waves } \\
k_{\mathrm{S}}=\frac{\omega}{\beta} & \text { Wavenumber for S waves } \\
k_\alpha=\sqrt{k_{\mathrm{P}}^2-k_z^2}, \quad k_\beta=\sqrt{k_{\mathrm{S}}^2-k_z^2} & \text { More wavenumbers } \\
H_{n \alpha}=H_n^{(2)}\left(k_\alpha r\right), \quad H_{n \beta}=H_n^{(2)}\left(k_\beta r\right) & \text { Shorthand for Hankel functions } \\
H_{0 \beta, l}=-k_\beta \gamma_l H_{1 \beta} & \begin{array}{l}
\text { Derivative of Hankel function } \\
\text { in the plane ( } l=1,2)
\end{array} \\
H_{0 \beta, z}=-\mathrm{i} k_z H_{0 \beta} & \begin{array}{l}
\text { Derivative of Hankel function } \\
\text { in the } z \text { direction }
\end{array} \\
B_n=k_\beta^n H_{n \beta}-k_\alpha^n H_{n \alpha} & \begin{array}{l}
B_n \text { functions (see end of sectior } \\
\text { for definitions and properties) }
\end{array} \\
\hat{\nabla}^2=\frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}-k_z^2 & \text { Laplacian }
\end{array}
$$


#### iii. Laplacian

考虑笛卡尔坐标下的切向量场的自然基底$\{\frac{\partial }{\partial x},\frac{\partial }{\partial y},\frac{\partial }{\partial z}\}$.自然标架$\bold{i},\bold{j},\bold{k}$

柱坐标系下:$\{\frac{\partial }{\partial r},\frac{\partial }{\partial \theta},\frac{\partial }{\partial z}\}$.幺正标架$e_r,e_{\theta},e_z$

坐标变换:$\left\{\begin{aligned}x &= r\cos\theta \\ y &= r\sin\theta \\z&=z \end{aligned}\right.$

注意到:
$$
\begin{aligned}
\frac{\partial }{\partial r} & = \cos\theta\frac{\partial }{\partial x} + \sin\theta\frac{\partial }{\partial y}\\
\frac{\partial }{\partial \theta} & = -r\sin\theta\frac{\partial }{\partial x} + r\cos\theta\frac{\partial }{\partial y}
\end{aligned}
$$
我们有:
$$
\begin{aligned}
e_r & = \cos\theta\bold{i} + \sin\theta\bold{j}\\
e_{\theta} & = -\sin\theta\bold{i} + \cos\theta\bold{j}\\
e_z &= \bold{k} 
\end{aligned}
$$
从而:
$$
\frac{\partial e_r}{\partial \theta} = e_{\theta},\; \frac{\partial e_{\theta}}{\partial \theta} = -e_r
$$
可以验证:
$$
\nabla = (\frac{\partial }{\partial x},\frac{\partial }{\partial y},\frac{\partial }{\partial z})' 
	   = \bold{i}\frac{\partial }{\partial x}+\bold{j}\frac{\partial }{\partial y}+\bold{k}\frac{\partial }{\partial z}
	   = e_r\frac{\partial }{\partial r} + \frac{1}{r}e_{\theta}\frac{\partial }{\partial \theta} + e_z\frac{\partial }{\partial z}
$$
进一步,得到:
$$
\begin{aligned}
\Delta = \nabla \cdot \nabla &= (e_r\frac{\partial }{\partial r} + \frac{1}{r}e_{\theta}\frac{\partial }{\partial \theta} + e_z\frac{\partial }{\partial z})^2\\
&= \frac{\partial^2 }{\partial r^2}+\frac{1}{r}e_{\theta}\frac{\partial }{\partial \theta}(e_r\frac{\partial }{\partial r}) +e_z\frac{\partial }{\partial z}(e_r\frac{\partial }{\partial r})\\
&\quad\; e_r\frac{\partial }{\partial r}(e_{\theta}\frac1r\frac{\partial }{\partial \theta})+\frac{1}{r^2}\frac{\partial^2 }{\partial \theta^2}+ e_z\frac{\partial }{\partial z}(e_{\theta}\frac1r\frac{\partial }{\partial \theta})\\
&\quad\; e_r\frac{\partial }{\partial r}(e_z\frac{\partial }{\partial z})+\frac1re_\theta\frac{\partial }{\partial \theta}(e_z\frac{\partial }{\partial z})+\frac{\partial^2 }{\partial z^2}\\
&=\frac{\partial^2 }{\partial r^2}+\frac{1}{r}e_\theta\frac{\partial e_r}{\partial \theta}\frac{\partial }{\partial r} + \frac{1}{r^2}\frac{\partial^2 }{\partial \theta^2}+\frac{\partial^2 }{\partial z^2}\\
&=\frac{\partial^2 }{\partial r^2}+\frac{1}{r}\frac{\partial }{\partial r} + \frac{1}{r^2}\frac{\partial^2 }{\partial \theta^2}+\frac{\partial^2 }{\partial z^2}
\end{aligned}
$$
其中,第三个等号后只保留了四项是因为$\frac{\partial e_k}{\partial k} = 0,(k=r,z),\frac{\partial e_z}{\partial k} = 0,(k=r,\theta)$.

#### iv. Solution of the Wave Equation  in Cylindrical Coordinates

**The Foundations of Acoustics || The Wave Equation in Cylindrical Coordinates and Its Applications **

```html
<embed id="pdfPlayer" src="D:\AcousticalWaveModels\Main part of the Foundations of Acoustics.pdf" type="application/pdf" width="100%" height="1200" >
```

<img src=".\AcousticalWaveModels.assets\Main part of the Foundations of Acoustics-1.png" alt="Main part of the Foundations of Acoustics-1" style="zoom:80%;" />

<img src=".\AcousticalWaveModels.assets\Main part of the Foundations of Acoustics-2.png" alt="Main part of the Foundations of Acoustics-1" style="zoom:80%;" />

#### v. Wave speed of tube

+ 我们使用以下的公式计算管波的速度:

$$
\begin{aligned}
& c_{\text {tube }}=\left[\rho_{\text {fluid }}\left(\frac{1}{B}+\frac{1}{M}\right)\right]^{-1 / 2}=\left[\frac{1}{c_{\text {fluid }}^2}+\frac{\rho_{\text {fluid }}}{M}\right]^{-1 / 2} \text { with: } \\
& M=\frac{E_{\text {pipe }} \cdot\left(a^2-b^2\right)}{2\left[\left(1+v_{\text {pipe }}\right)\left(a^2+b^2\right)-2 v_{\text {pipe }} b^2\right]}
\end{aligned}
$$

​		$a$:管道的外半径

​		$b$:管道的内半径

​		$\nu_{pipe}$:管道材料的泊松比

​		$E_{pipe}$:管道材料的弹性模量,
$$
E_{pipe} = 2\mu_{pipe}(1+\nu_{pipe})=(c_{s_{pipe}}^2\rho_{pipe}(1+\nu_{pipe})),\text{where}\; c_s = c_p\sqrt{\frac{1-2\nu}{2(1-\nu)}}
$$


+ 如果有多种固体限制流体:

$$
c_{\text {tube }}=\left[\frac{1}{c_{\text {fluid }}^2}+\frac{\rho_{\text {fuid }}}{\sum_{i=1}^{\text {lavers }} \mathrm{M}_i}\right]^{-1 / 2}
$$

​	As noted in White for a thin tube $M = \frac{E_{pipe}h_{pipe}}{2b}$, where $h_{pipe} = a-b$ and for an infinite surrounding medium $M = \mu_{pipe}$ 





