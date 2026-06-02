# 現代制御に変換
## $\frac{K}{Ts+1}$の変換
$\frac{K}{Ts+1}$から、$T\dot{y}+y=Ku$

状態: $\boldsymbol{x}=\begin{bmatrix}x\end{bmatrix}$, 入力: $u$

$$\dot{\boldsymbol{x}}=\begin{bmatrix}-\frac{1}{T}\end{bmatrix}\boldsymbol{x}+\begin{bmatrix}\frac{K}{T}\end{bmatrix}u$$
$$y=\begin{bmatrix}1\end{bmatrix}\boldsymbol{x}$$

## $\frac{K}{(Ts+1)s}$の変換
$\frac{K}{(Ts+1)s}$から、$T\ddot{y}+\dot{y}=Ku$

状態: $\boldsymbol{x}=\begin{bmatrix}x\\\dot{x}\end{bmatrix}$, 入力: $u$

$$\dot{\boldsymbol{x}}=\begin{bmatrix}0&1\\0&-\frac{1}{T}\end{bmatrix}\boldsymbol{x}+\begin{bmatrix}0\\\frac{K}{T}\end{bmatrix}u$$
$$y=\begin{bmatrix}1&0\end{bmatrix}\boldsymbol{x}$$

# シミュレーションの為に離散化する
$$\dot{\boldsymbol{x}}=A\boldsymbol{x}+Bu(k),y=\boldsymbol{C}^T\boldsymbol{x}$$
に対して簡単な方法で離散化すると
$$\frac{\boldsymbol{x}(k+1)-\boldsymbol{x}(k)}{dt}=A\boldsymbol{x}(k)+Bu(k)$$
$$\therefore \boldsymbol{x}(k+1)=(I+dtA)\boldsymbol{x}(k)+dtBu$$

## $\frac{K}{Ts+1}$の変換
$$x_{k+1}=\left(1-\frac{dt}{T}\right)x_k+\frac{Kdt}{T}u_k$$

## $\frac{K}{(Ts+1)s}$の変換
$$x_{k+1}=x_k+dt\dot{x}_k,\dot{x}_{k+1}=\left(1-\frac{dt}{T}\right)\dot{x}_k+\frac{Kdt}{T}u_k$$

参考にした資料  
[状態方程式](https://www.youtube.com/watch?v=xDa0X7YExpc)  
[離散化](https://www.youtube.com/watch?v=kqmG-KIIzn4)
