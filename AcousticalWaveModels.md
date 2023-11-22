# Acoustical Wave Models

## Ⅰ. Simplified Model and Layered Models

Ref : Acoustical wave propagation in buried water filled pipes(2005).

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

![image-20231120095943848](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120095943848.png)

以上的PDE的解为:

![image-20231118124625632](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118124625632.png)

根据物理模型的假设:***波从源向外移动，并且在靠近源的地方具有有限的强度***,解化简为:

![image-20231118125759356](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118125759356.png)

根据Simplified Model中的假设,边界条件:

![image-20231118125843356](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118125843356.png)

将此条件代入$\phi(r,\theta,z)$就得到:

![image-20231118131140499](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118131140499.png)

###### b. Solution of simplified model

以上的分析告诉了我们解具有的形式,现在考虑添加载荷项之后的方程的解.

+ 以$S(r,\theta,k_z,w)$表示源的强度,并利用Fourier-Bessel级数(Fourier级数和Bessel级数的张量)展开:

![image-20231118131556668](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118131556668.png)

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

![image-20231118133858347](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231118133858347.png)

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

+ 给定轴向波数$k_z$和频率$w$,单个圆柱层内部某点位移矢量的弹性波方程的特定解具有以下形式:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120111706259.png" alt="image-20231120111706259" style="zoom:80%;" />

![image-20231120111730383](C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120111730383.png)

​	$\overline{u}$表示频率-波数域的解,$\widetilde{u}$意味着$z,\theta$的变化已经分离.

​	其中$c_1,c_2$是任意常数,$T_n,J,Y$如以下的Table 2所示:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120111911855.png" alt="image-20231120111911855" style="zoom:80%;" />

+ 圆柱表面上的应力

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120112325763.png" alt="image-20231120112325763" style="zoom:80%;" />

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120112334964.png" alt="image-20231120112334964" style="zoom:80%;" />

​	$F^{(1)},F^{(2)}$见Table 3, 它们分别由第一第二类Bessel函数构造

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120112615390.png" alt="image-20231120112615390" style="zoom:80%;" />

##### (2)Layered Models

###### a. Single layer

最外层是孤立的自由层,单层外半径和内半径分别为$r_1,r_2$,评估这两个表面上的位移和应力，将每弧度的牵引力定义为应力和界面半径的乘积,并将两者写成矩阵形式,得到：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114002490.png" alt="image-20231120114002490" style="zoom:80%;" />

其中下标表示计算矩阵的位置,上标表示使用的Bessel函数的类型.

+ 消去$c_1,c_2$

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114110787.png" alt="image-20231120114110787" style="zoom:80%;" />

​	以下$K$称作对称刚度(阻抗)矩阵symmetric stiffness (or impedance) matrix of the cylindrical layer.

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114136948.png" alt="image-20231120114136948" style="zoom:80%;" />

###### b. Unbounded external region

对于无界均匀空间内的圆柱形空腔,外部区域可以被视为外半径无限大的层.在这种情况下,$c_2$ 必须设置为零（以满足无穷远的辐射和有界条件,并在矩阵中使用第二汉克尔函数而不是贝塞尔函数.因此,外部区域的 $3\times3$ impedance matrix:
$$
K_{ext} = -rFH^{-1}
$$
$H,F$分别参考Table2,3两者都必须使用在外部区域半径 $r$ 处计算的第二汉克尔函数来构建.

###### c. Layered system

从外部区域的刚度矩阵开始,为每一层创建层矩阵,得到以下的分块三对角阵:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114346713.png" alt="image-20231120114346713" style="zoom:80%;" /> 

##### (3)Fluid-pipes-soil model

在这部分,将一步步优化我们的模型:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114709704.png" alt="image-20231120114709704" style="zoom: 50%;" />

+ 对于以上的系统,我们有:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120114727620.png" alt="image-20231120114727620" style="zoom:80%;" />

+ +  $p_1$作用在流固界面上的径向压力
  + $p_2$:作用于任何其他自由度的压力
  + $u_1$:流固界面的径向位移
  + $u_2$:所有其他自由度的位移
  + $K_{ii}$:the sub-matrices of the total stiffness matrix connecting the pressures of the fluid-solid interface and all the remaining degrees of freedom to their respective displacements
  + $K_{ij}$:the sub-matrices of the total stiffness matrix expressing the pressures of the fluid-solid interface and all the remaining degrees of freedom to their unrelated displacements

系统的刚度矩阵用来求解$p_1$,

+ 无限流体介质将分为两部分:一层流体核心和一层无限延伸流体.它们的分离界面的半径等于管道的内半径,如下图所示：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120115413464.png" alt="image-20231120115413464" style="zoom:50%;" />
$$
p^* = -K_{fe}u_r^*
$$

+ + $p^*$:作用在界面上的压力（由于流体核心中的来源）
  + $u_r^*$:界面向外位移
  + $K_{fe}$:流体外层的刚度矩阵

+ 在实际的圆柱形布局中，外层不是无限的流体，而是复杂的圆柱形分层系统.假设流体层中的源在核心流体与外部系统之间的界面上引起的应力等于$\sigma_{1r}$

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120120020110.png" alt="image-20231120120020110" style="zoom:80%;" />

+ 考虑到内部流体的刚度没有改变,无限流体和完整系统模型之间的位移差异仅是由于施加压力的差异造成的.无限流体和完整系统模型中的位移和应力之间的关系将是（如图所示）：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120120114672.png" alt="image-20231120120114672" style="zoom:50%;" />


$$
\begin{aligned}
\Delta p &=K_{fi}\Delta u \Leftrightarrow \\
p^{*}-(-\sigma_{1r}) &= K_{fi}(u_r^*-u_{1r})\Leftrightarrow\\
\sigma_{1r} &= -r^*+K_{fi}u_r^*-K_{fi}u_{rl}\\
\sigma_{1r} &=(K_{fe}+K{fi})u_r^*-K_{fi}u_{r1}
\end{aligned}
$$


+ 如果系统上没有施加其他应力，则完整模型的方程现在可以写成矩阵形式：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120120156774.png" alt="image-20231120120156774" style="zoom:80%;" />

+ 上述刚度矩阵是包含流体的系统的刚度矩阵,它是通过将各个自由度连接在一起来计算的.这组方程可以求解界面的径向位移为：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120121005565.png" alt="image-20231120121005565" style="zoom:80%;" />

​	其中,$K_{cons}$为是系统沿自由度的合并矩阵

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120121055688.png" alt="image-20231120121055688" style="zoom:80%;" />

+ 则界面上的压力将为：

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120121108469.png" alt="image-20231120121108469" style="zoom:80%;" />

+ 为了找到流体-固体界面处的压力,唯一缺少的一项是具有相同半径但位于无限延伸流体中的界面的位移 $u_r^*$.这可以通过求解无限延伸介质的圆柱坐标中的 Helmholtz equation 来实现, 从而我们得到:(为了方便计算,我们假设源在轴线上,这样不需要考虑方位角$\theta$)

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120121303967.png" alt="image-20231120121303967" style="zoom:80%;" />

+ 此时径向位移(关于波数$k_z$,频率$w$)的函数

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120121339515.png" alt="image-20231120121339515" style="zoom:80%;" />

+ 在半径为 $R_c$ 的人工“界面”,径向位移为:

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120121544466.png" alt="image-20231120121544466" style="zoom:80%;" />

​		至此,我们就得到了$\sigma_{1r}$

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

###### Example

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231120135142828.png" alt="image-20231120135142828" style="zoom:80%;" />

#### iii. Algorithm

我们根据以下参数来选择需要的模型,具体的算法步骤参考1.Simplified Model,其中的 $L$ 是所考虑的最大频率与信号“频率”(持续时间的倒数)的比率,$\xi$表示damping ratio.

<img src="C:\Users\Dell\AppData\Roaming\Typora\typora-user-images\image-20231119163700365.png" alt="image-20231119163700365" style="zoom:80%;" />