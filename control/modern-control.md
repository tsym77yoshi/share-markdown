# 現代制御に変換
## $\frac{K}{Ts+1}$の変換
$\frac{K}{Ts+1}$から、$T\dot{y}+y=Ku$

状態: $\boldsymbol{x}=\begin{pmatrix}x\end{pmatrix}$, 入力: $u$

$$\dot{\boldsymbol{x}}=\begin{pmatrix}-\frac{1}{T}\end{pmatrix}\boldsymbol{x}+\begin{pmatrix}\frac{K}{T}\end{pmatrix}u$$
$$y=\begin{pmatrix}1\end{pmatrix}\boldsymbol{x}$$

## $\frac{K}{(Ts+1)s}$の変換
$\frac{K}{(Ts+1)s}$から、$T\ddot{y}+\dot{y}=Ku$

状態: $\boldsymbol{x}=\begin{pmatrix}x\\\dot{x}\end{pmatrix}$, 入力: $u$

$$\dot{\boldsymbol{x}}=\begin{pmatrix}0&1\\0&-\frac{1}{T}\end{pmatrix}\boldsymbol{x}+\begin{pmatrix}0\\\frac{K}{T}\end{pmatrix}u$$
$$y=\begin{pmatrix}1&0\end{pmatrix}\boldsymbol{x}$$

# シミュレーションの為に離散化する
$$\dot{\boldsymbol{x}}=A\boldsymbol{x}+Bu,y=\boldsymbol{C}^T\boldsymbol{x}$$
に対して簡単な方法で離散化すると
$$\frac{\boldsymbol{x}(k+1)-\boldsymbol{x}(k)}{dt}=A\boldsymbol{x}(k)+Bu$$
$$\therefore \boldsymbol{x}(k+1)=(I+dtA)\boldsymbol{x}(k)+dtBu$$

## $\frac{K}{Ts+1}$の変換
$$x_{k+1}=\left(1-\frac{dt}{T}\right)x_k+\frac{Kdt}{T}u$$

## $\frac{K}{(Ts+1)s}$の変換
$$x_{k+1}=x_k+dt\dot{x}_k,\dot{x}_{k+1}=\left(1-\frac{dt}{T}\right)\dot{x}_k+\frac{Kdt}{T}u$$

参考にした資料  
[慶應YouTube](https://www.youtube.com/watch?v=xDa0X7YExpc)  
[離散化についてのYouTube]()
