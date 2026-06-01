# 角速度PI制御を解く
-# D項は二階微分になり、データがガタつくので使ってはいけない
## 制御対象
$$\frac{K}{Ts+1}$$
## コントローラ
$$(K_p+\frac{K_I}{s})$$
## 閉ループ
$$\frac{\frac{K}{Ts+1}(K_p+\frac{K_I}{s})}{1+\frac{K}{Ts+1}(K_p+sK_d)}$$
$$=\frac{K(K_p+\frac{K_I}{s})}{Ts+1+K(K_p+\frac{K_I}{s})}$$
$$=K\frac{K_ps+K_I}{Ts^2+(1+KK_p)s+KK_I}$$
### $K_I=0$のとき
$$=\frac{\frac{KK_p}{1+KK_p}}{\frac{T}{1+KK_p}s+1}$$
で、確かに時定数が減っている！ステップ応答は
$$=-\frac{\frac{KK_p}{1+KK_p}\frac{T}{1+KK_p}}{\frac{T}{1+KK_p}s+1}+\frac{\frac{KK_p}{1+KK_p}}{s}$$
$$=-\frac{KK_p}{1+KK_p}e^{-\frac{1+KK_p}{T}t}+\frac{KK_p}{1+KK_p}$$
$$=\frac{KK_p}{1+KK_p}(1-e^{-\frac{t}{(\frac{T}{1+KK_p})}})$$

# 角度PD制御を解く
## 制御対象
$$\frac{K}{(Ts+1)s}$$
## コントローラ
$$(K_p+sK_d)$$
## 閉ループ
$$\frac{\frac{K}{(Ts+1)s}(K_p+sK_d)}{1+\frac{K}{(Ts+1)s}(K_p+sK_d)}$$
$$=\frac{K(K_p+sK_d)}{(Ts+1)s+K(K_p+sK_d)}$$
$$=K\frac{K_ds+K_p}{Ts^2+(1+KK_d)s+KK_p}$$

$(1+KK_d)^2-4TKK_p\geq 0$でないと不安定なシステムになる  

$K_p=0$だとうまくいく->そんなわけないのでむだ時間の導入($e^{-Ls}$)が必要だった?
