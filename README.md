下文中，我们假设:  
$g:R^3 \rightarrow R^3$
是刚体旋转函数
我们讨论那些假设可以满足刚体旋转，其中一个直观的特性就是模长不变性：
假设$a,b \in R^3$,$g$满足: $||a-b||=||g\left(a\right)-g\left(b\right)||$

### 命题1
如果g满足模长不变性，则$g$是线性变换，即存在$3\times 3$矩阵$R$和$3$维列向量$t$,使得 $g\left(x\right)=Rx+t$,且$RR^T=I$
##### 证明  
假设$f\left(x\right)=g\left(x\right)-g\left(0\right)$，那么$||x||=||x-0||=||f(x)-f(0)||=|||g(x)|$,$||a-b||=||f(a)-f(b)||=||g(a)-g(b)||$，进而 $a^Tb=g(a)^Tg(b)$。假设$e_1=[1,0,0]^T,e_2=[0,1,0]^T,e_3=[0,0,1]^T$，由$a^Tb=g(a)^Tg(b)$可知$g(e_1),g(e_2),g(e_3)$也是一组正交基。对于任意3维列向量$a=[a_1,a_2,a_3]^T$，显然$a$可以由$e_1,e_2,e_3$唯一线性表出: $a=a_1e_1+a_2e_2+a_2e_3$,$a_i=a^Te_i=g(a)^Tg(e_i)$，所以$g(a)=a_1g(e_1)+a_2g(e_2)+a_3g(e_3)=[g(e_1),g(e_2),g(e_3)]a$，记$R=[g(e_1),g(e_2),g(e_3)]$,那么$g(a)=Ra$，记$t=g(0)$，那么就有$f(x)=g(x)+g(0)=Rx+t$，容易验证$R^TR=[g(e_1),g(e_2),g(e_3)]^T[g(e_1),g(e_2),g(e_3)]=[e_1,e_2,e_3]^T[e_1,e_2,e_3]=I$

### 命题2
假设$R^TR=I$,那么$det(R)=1$的充要条件是: 对于任意的三维列向量$a,b$，有$R(a\times b)=(Ra)\times(Rb)$
##### 证明
###### 必要性
记$e_1=[1,0,0]^T,e_2=[0,1,0]^T,e_3=[0,0,1]^T$，  
等式左边:  
$R(a\times b)=R((a_ie_i)\times(b_je_j)))=(a_ib_j)(R(e_i\times e_j))$  
同理，等式右边:  
$(Ra)\times(Rb)=(a_ib_j)((Re_i)\times (Re_j))$  
因此我们只要验证$R(e_i\times e_j)=(Re_i)\times (Re_j)$即可。  
例如验证$R(e_1\times e_2)=(Re_1)\times (Re_2)$，根据R的性质，容易知道$e_1\times e_2=e_3$,因此$R(e_1\times e_2)=Re_3$,即:$R(e_1\times e_2)$是R的第三个列向量。而$Re_1$是R的第一个列向量，$Re_2$是R的第二个列向量，进而$(Re_1)\times (Re_2)$就是R的第三个列向量，等式得证。其它的case验证方法类似。  
顺便一提，假设$R=[r_1,r_2,r_3]$,等式$r_1\times r_2=r_3$可以这样证明:$det(R)=r_3^T(r_1\times r_2)=1$，$||r_3||=1$,$||r_1\times r_2||<=||r_1||\cdot||r_2||=1$,因此$r_3=r1\times r_2$  
###### 充分性
令$a=[1,0,0]^T,b=[0,1,0]^T, R=[r_1,r_2,r_3]$，则$a\times b=[0,0,1]^T,R(a\times b)=r_3, Ra=r_1, Rb=r_2, (Ra)\times(Rb)=r_1\times r_3$,因此$r_3=r_1\times r_2, det(R)=r_3\cdot(r_1\times r_2)=r_3\cdot r_3$,由$R^TR=I$可知，$det(R)=r_3\cdot r_3=1$

