



# Acoustical Wave Models

## Ⅰ. Simplified Model and Layered Models

Ref : **Acoustical wave propagation in buried water filled pipes(2005)**. 

​		 **Fundamental Solutions in Elastodynamics**

### 1.Simplified Model

#### i. Main idea

+ The pipe will be considered to be much stiffer than the water it contains, in which case the fluid is surrounded by a cylindrical boundary that allows no motions in the radial direction.(管道将被认为比其所容纳的水硬得多，在这种情况下，流体被圆柱形边界包围，不允许沿径向方向运动)

*Why we need this simplified model?*

*如果波可以穿过不止一种介质，特别是在固相和液相之间存在相互作用的情况下，在圆柱坐标系中严格制定声音传播是一个相当困难的问题*.(当然这种困难的问题在后面也有所讨论)

#### ii. Mathematical preliminaries and application

##### (1)Laplacian in cyclindrical coordinates

圆柱坐标系下的拉普拉斯算子:
$$
\nabla^2 f = \frac {\part^2 f}{\part r^2}+\frac 1 r\frac{\part f}{\part r}+\frac{1}{r^2}\frac{\part^2 f}{\part \theta^2}+\frac{\part^2f}{\part z^2}
$$

上式只需利用chain rule即可,可以在任何一本数学分析/微积分的教材中找到,我们将在 wave equation 和 Helmholtz equation中多次使用它.

##### (2)Bessel function

参考维基百科上的介绍: [Bessel function](https://zh.wikipedia.org/zh-hans/%E8%B4%9D%E5%A1%9E%E5%B0%94%E5%87%BD%E6%95%B0)

+ Bessel函数是Bessel方程的解

$$
x^2y''+xy'+(x^2-\alpha^2)y=0
$$

有三类贝塞尔函数,根据我们的需要进行选取即可.

+ Bessel函数的正交性:

由于贝塞尔方程对应的作用算符除以$x$后便是一个**自伴算子**(self-adjoint operator),所以它的解在适当边界条件下须满足正交性关系.特别地,有：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120095641181.png" alt="image-20231120095641181" style="zoom: 67%;" />

##### (3)Acoustic wave equation

参考维基百科上的介绍: [Acoustic wave equation](https://en.wikipedia.org/wiki/Acoustic_wave_equation)

###### a. The form of solution

$$
\nabla^2 \phi = \frac{1}{c^2}\frac{\part^2\phi}{\part t^2}
$$

其中$c$是声速,$\phi$表示***abstract scalar field***,可以理解为***Velocity Potential***,

得到$\phi$后,$\bold{u} = \nabla\phi,p = -\rho \frac{\part\phi}{\part t} $.

利用(1)Laplacian in cyclindrical coordinates,得到:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120095943848.png" alt="image-20231120095943848" style="zoom: 67%;" />

以上的PDE的解为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118124625632.png" alt="image-20231118124625632" style="zoom:80%;" />

根据物理模型的假设:***波从源向外移动，并且在靠近源的地方具有有限的强度***,解化简为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118125759356.png" alt="image-20231118125759356" style="zoom:80%;" />

根据Simplified Model中的假设,边界条件:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118125843356.png" alt="image-20231118125843356" style="zoom:80%;" />

将此条件代入$\phi(r,\theta,z)$就得到:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118131140499.png" alt="image-20231118131140499" style="zoom:80%;" />

###### b. Solution of simplified model

以上的分析告诉了我们解具有的形式,现在考虑添加载荷项之后的方程的解.

+ 以$S(r,\theta,k_z,w)$表示源的强度,并利用Fourier-Bessel级数(Fourier级数和Bessel级数的张量)展开:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118131556668.png" alt="image-20231118131556668" style="zoom:80%;" />

其中,$k_{nj}:J_n'(k_{nj}R) = 0$

+ 由于Fourier-Bessel级数的正交性,Fourier系数可以由以下公式计算:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118131744822.png" alt="image-20231118131744822" style="zoom:67%;" />

+ 添加载荷项之后的方程为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133518345.png" alt="image-20231118133518345" style="zoom:80%;" />

​		其中

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133526474.png" alt="image-20231118133526474" style="zoom:80%;" />

+ 为了求解以上的方程,考虑$\phi$的Fourier-Bessel展开(注意,此时考虑的$\phi$是频域$k_z,w$上的函数):

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133621601.png" alt="image-20231118133621601" style="zoom:80%;" />

+ 代入添加了载荷项之后的方程,有:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133723341.png" alt="image-20231118133723341" style="zoom:80%;" />

+ 由线性无关性:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133858347.png" alt="image-20231118133858347" style="zoom: 80%;" />

​		整理后得到:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133933683.png" alt="image-20231118133933683" style="zoom:80%;" />

​		注意到$J_n''+\frac1rJ_n'+(k_{nj}^2-(\frac{n}{r})^2J_n$即为Bessel方程的左端项,从而为0;

+ 解得

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118134113878.png" alt="image-20231118134113878" style="zoom:80%;" />

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118134143144.png" alt="image-20231118134143144" style="zoom:80%;" />

+ 以上的$A_{nj},B_{nj}$是$\phi$中所有包含轴向波数$k_z$的项,进行Fourier逆变换:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118135408030.png" alt="image-20231118135408030" style="zoom:80%;" />

​	此积分可以由留数定理(积分区域取$R\rightarrow-R(Re^{i\pi})\stackrel{cycle}{\longrightarrow}Re^{i2\pi}$)计算:

​	<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118140545384.png" alt="image-20231118140545384" style="zoom:80%;" />

+ 最终得到的解为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118141205276.png" alt="image-20231118141205276" style="zoom:80%;" />

现在我们只需要求出$S(r,\theta,k_z,w)$中的对应系数$a_{nj},b_{nj},k_{nj}$即可,接下来我们来确定这件事.

##### (4)Specific form of the solution

###### a. off-center point source

+ 假设源偏离中心的距离为$a$,如下图所示:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120102630687.png" alt="image-20231120102630687" style="zoom:80%;" />

+ 源的强度函数表达为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120102543877.png" alt="image-20231120102543877" style="zoom:80%;" />

​	注意,这是一个频域$(w)$上的函数,$\delta(\cdot)$表示[狄拉克函数](https://zh.wikipedia.org/zh-hans/%E7%8B%84%E6%8B%89%E5%85%8B%CE%B4%E5%87%BD%E6%95%B0),它是一个分布函数,可以用标准正态分布方差趋于$0$的序列的弱极限来表示.狄拉克函数在信号处理上也被称为**单位脉冲符号**或**单位脉冲函数**.

​	以上的表达式是为了说明我们在某个点发出了信号.

+ 源的强度满足以下表达式:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120103502107.png" alt="image-20231120103502107" style="zoom:80%;" />

+ 我们计算出对应的$a_{nj},b_{nj}$:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120103650147.png" alt="image-20231120103650147" style="zoom:80%;" />

+ 最终得到$\phi$的表达式

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120103729436.png" alt="image-20231120103729436" style="zoom:80%;" />

以上的计算需要在很大的范围内进行双重求和,代价比较昂贵.

###### b. center point source

+ $a=0$时,源的强度函数表达为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120103856713.png" alt="image-20231120103856713" style="zoom:80%;" />

+ 此时非零的系数仅有:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120103934772.png" alt="image-20231120103934772" style="zoom:80%;" />

+ $\phi$的表达式(频域)

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120104004584.png" alt="image-20231120104004584" style="zoom:80%;" />

+ $p=\rho \frac{\part\phi}{\part t}$的表达式(频域)

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120104054723.png" alt="image-20231120104054723" style="zoom:80%;" />

​	对于以上的表达式,注意到管道的normal modes为:$k_{0j} = w_{0j}/c=z_{0j}/R$,即

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120104405084.png" alt="image-20231120104405084" style="zoom:80%;" />

#### iii. Algorithm

维基百科:[短时距傅里叶变换](https://zh.wikipedia.org/zh-hans/%E7%9F%AD%E6%99%82%E8%B7%9D%E5%82%85%E7%AB%8B%E8%91%89%E8%AE%8A%E6%8F%9B)

##### (1)Exponential Window Method

###### a. EWM数学原理

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231119140326445.png" alt="image-20231119140326445" style="zoom:50%;" />

###### b. EWM流程图

![image-20231119124640936](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231119124640936.png)



###### c. EWM算法流程

***One. Acoustical wave propagation in buried water filled pipes*** 

+ Calculate the FFT of the forcing function
+ Multiply it by a falling exponential window
+ Calculate the transfer function for the complex frequency
+ Multiply the FFT of the forcing function and the transfer function to get the response function
+ Do the inverse FFT
+ Multiply the resulting displacement by a rising exponential window with the same parameter $\eta$ to get the actual response

$EWM:\text{force function }f(t)\stackrel{FFT}{\longrightarrow}F(w)\stackrel{FEW}{\longrightarrow}F(\overline{w})\xrightarrow[multiply]{calculate H(w)}\phi^*(r,\theta,z,\overline{w})\stackrel{IFFT}{\longrightarrow}\phi^*(r,\theta,z,t)\stackrel{REW}{\longrightarrow}\phi(r,\theta,z,t)$

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
9. 如果计算出的$\Delta t$不能很好地指示time-history曲线的形状,可以考虑进行插值(**Ref**:***Brigham EO (1988) The fast Fourier transform and its applications. Prentice Hall, New Jersey***).

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

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231119160142473.png" alt="image-20231119160142473" style="zoom: 80%;" />

### 2.Layered Models

从**Chapter6(Page 55)**,开始讨论由若干个同心圆柱层组成的系统:

+ Single layer(最外层是孤立的自由层,单层外半径和内半径分别为$r_1,r_2$)
+ Unbounded external region(外部被视为无限大的层)
+ Layered system(多层系统,可以是无界的外部区域)

我们所需要的流体-管道-土壤模型(下图,Page 64 of thesis),属于case 2: Unbounded external region.

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231119204312007.png" alt="image-20231119204312007" style="zoom:50%;" />

#### i. Main idea

+ 考虑一个由$N_l-1$个任意厚度的同心圆柱层组成的系统，我们从内到外对其$N_l$个界面进行编号.可选择无限大的外部区域可以围绕这些层.将假定每层中的材料特性与方位角$\theta$无关并且在每个圆柱形层内是均匀的。

#### ii. Mathematical preliminaries

##### (1)General case

***As shown by Kausel [Compendium of Fundamental Solutions in Elastodynamics, Cambridge University Press, in print],***

+ 给定轴向波数$k_z$和频率$w$,单个圆柱层内部某点位移矢量的特定解具有以下形式

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130215704730.png" alt="image-20231130215704730" style="zoom:80%;" />

![image-20231130215733461](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130215733461.png)



+ 圆柱表面上的应力

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130215851228.png" alt="image-20231130215851228" style="zoom:80%;" />

##### (2)Layered Models

###### a. Single layer

最外层是孤立的自由层,单层外半径和内半径分别为$r_1,r_2$,分别计算这两个表面上的位移和应力,得到：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130215924236.png" alt="image-20231130215924236" style="zoom:80%;" />

其中下标表示计算矩阵的位置,上标表示使用的Bessel函数的类型.

+ 消去$a_1,a_2$

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130220116440.png" alt="image-20231130220116440" style="zoom:80%;" />

​	$K$称作刚度矩阵:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130220139152.png" alt="image-20231130220139152" style="zoom:80%;" />

###### b. Unbounded external region

对于无界均匀空间内的圆柱形空腔,外部区域可以被视为外半径无限大的层.在这种情况下,$a_2$ 必定为零.因此,外部区域的 $3\times3$ 刚度矩阵:
$$
K_{ext} = -rF_n^{(2)}(H_n^{(2)})^{-1}
$$
###### c. Layered system

从外部区域的刚度矩阵开始,为每一层创建层矩阵,得到以下的分块三对角阵:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114346713.png" alt="image-20231120114346713" style="zoom:80%;" /> 

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130220457504.png" alt="image-20231130220457504" style="zoom:80%;" />



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
此外,由于外部区域没有源,因此齐次参考问题的应力满足平衡条件
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

以上的刚度矩阵,见**Table 1 Table 2**

###### b. step 2

柱坐标系下的[Green's functions](https://zh.wikipedia.org/wiki/%E6%A0%BC%E6%9E%97%E5%87%BD%E6%95%B8)

Let $g_j (r, r') = g_j (r, r', t)$ or $g_j (r, r') = g_j (r, r', w)$ be the Green’s function for a receiver placed at location $r$ due to an impulsive or harmonic source, a point load $P = 1$ acting at location $r'$ in some principal direction $j$.

+  When the Green’s functions for a point load acting on the cylindrical axis (i.e.,$ r' = 0$) at depth $z'$ are expressed in cylindrical coordinates, they have the general form

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130223608507.png" alt="image-20231130223608507" style="zoom:80%;" />

以上涉及到的字母,参考**Table 3**

其中,$g_{ij}$表示$j$方向的单位载荷对于$i$方向的影响.

如果求和$\bold{g_{j}} = g_i^je^{i}$($g_i^j = g_{ij}$)则表示$j$方向的单位载荷对于所有方向的影响,在三维空间中,$\bold{g_j}$是个三维列向量.

(通常,我们以$\bold{i},\bold{j},\bold{k}$表示Cartesian coordinates下的标准正交基,$\bold{r},\bold{t},\bold{k}$表示柱面坐标系的标准正交基)

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130225524076.png" alt="image-20231130225524076" style="zoom:80%;" />

$ u =\sum \bold{g_x}$

###### c . Result

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120135142828.png" alt="image-20231120135142828" style="zoom:80%;" />



#### iii. Algorithm

我们根据以下参数来选择需要的模型,具体的算法步骤参考1.Simplified Model,其中的 $L$ 是所考虑的最大频率与信号“频率”(持续时间的倒数)的比率,$\xi$表示damping ratio.

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231119163700365.png" alt="image-20231119163700365" style="zoom:80%;" />

### 3. Appendix

#### i. DFT&FFT

***为了方便,以下所有的下标从零开始.***

##### (1) 正交基

对于内积空间$(\C^N,(\cdot,\cdot))$,其中内积为标准内积$(x,y) = x'\overline{y} = \sum_{j=0}^{N-1}x_j\overline{y_j}$,

 $\{e_k = (e^{iwk \cdot 0},e^{iwk \cdot 1},...,e^{iwk \cdot(N-1)})\}_{k=0}^{N-1}, \;w = \frac{2\pi}{N}$构成了一组正交基:

*Proof:* 记$w_1 = e^{iw} = e^{i\frac{2\pi}{N}}$为$1$的$N$次方根.

+ $(e_k,e_l) = \sum_{j=0}^{N-1} w_1^{kj}w_1^{-lj} = \sum_{j=0}^{N-1}w_1^{j(k-l)} $

+ 如果$k=l$,$(e_k,e_l) = \sum_j 1 = N$

+ 如果$k\neq l$,$(e_k,e_l) = \sum_{j} (w_1^{k-l})^j = 0$ 这是由$1+z+z^2+\cdots+z^{N-1} = \frac{Z^N-1}{z-1}$,令$z = w_1^{k-l}$得到.

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

##### (4) DFT中的w

对于一段长度为$T$s的音频,采样率为$f_s$,此时得到了向量的长度为$N = T\cdot f_s$

此时,傅里叶变换中对应的$w$应该是什么?

对于信号:

| $t/\frac{1}{f_s}$ |  $0$   |  $1$   | $\cdots$ |  $N-1$   |
| :---------------: | :----: | :----: | :------: | :------: |
|      $f(t)$       | $x[0]$ | $x[1]$ | $\cdots$ | $x[N-1]$ |

经过FFT之后得到:

| $F(w)$ | $X[0]$ | $X[1]$ | $\cdots$ | $X[N-1]$ |
| :----: | :----: | :----: | :------: | :------: |

+ 以$t_*$表示单位为$s$的时间,从而$ t = t_*/f_s$
+ $x = \sum_k X[k]e_k$,其中$e_k$是$e^{i\frac{2\pi}{N}k}$生成的,

$$
e^{i\frac{2\pi}{N}k t_*} =e^{i\frac{2\pi}{N}kf_s \cdot t}
$$

+ 即$w_k = \frac{2\pi}{N}f_s k = \frac{2\pi}{T}k$

#### ii. Table

##### (1) Table 1

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231201125248157.png" alt="image-20231201125248157" style="zoom:80%;" />

##### (2) Table 2

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231201125420334.png" alt="image-20231201125420334" style="zoom:80%;" />

##### (3) Table 3

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130223705348.png" alt="image-20231130223705348" style="zoom:80%;" />

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231130223746248.png" alt="image-20231130223746248" style="zoom:80%;" />

#### iii. 管波波速

+ 我们使用以下的公式计算管波的速度:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120135305467.png" alt="image-20231120135305467" style="zoom:80%;" />

​		$a$:管道的外半径

​		$b$:管道的内半径

​		$\nu_{pipe}$:管道材料的泊松比

​		$E_{pipe}$:管道材料的弹性模量,
$$
E_{pipe} = 2\mu_{pipe}(1+\nu_{pipe})=(c_{s_{pipe}}^2\rho_{pipe}(1+\nu_{pipe})),\text{where}\; c_s = c_p\sqrt{\frac{1-2\nu}{2(1-\nu)}}
$$


+ 如果有多种固体限制流体:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120140102744.png" alt="image-20231120140102744" style="zoom:80%;" />

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120140115941.png" alt="image-20231120140115941" style="zoom:80%;" />



