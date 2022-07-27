# 实验名称
forge signature

# 实验简介
forge a signature to pretend that you are Satoshi

# 实验完成人
权周雨 

学号：202000460021 

git账户名称：baekhunee

# 实验思路

## ECDSA验签过程
![image](https://user-images.githubusercontent.com/105578152/181155330-06206b7c-270b-440c-99f0-c03c7d0a9eb8.png)

其中Q_A为公钥。

## 伪造签名过程
1、重新选择a、b，计算:
```
(x2,y2) = a * G + b * Q_A
```

2、计算：
```
r1 = x2 mod n
b1 = b^(-1) mod n
e1 = r1 * a * b1 mod n
s1 = r1 * b1 mod n
```
(r1,s1)即为伪造的签名。此外，该算法为概率算法，成功概率与选取的随机数有关。

# 部分代码说明
## def gcd(a,b)
辗转相除法求最大公因子

## def xgcd(a, m)
扩展欧几里得算法求模逆

## def epoint_add(P,Q)
椭圆曲线上的加法

## epoint_mul(k, g)
椭圆曲线上的点乘

## def signature(m)
ECDSA签名算法

## def verify(r,s)
ECDSA验签算法

## def forge_signature(r,s)
伪造签名

# 测试截图
![image](https://user-images.githubusercontent.com/105578152/181156774-6c4125ce-324b-4ef8-b561-bc5e323780d3.png)
