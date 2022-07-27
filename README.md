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
1、重新选择a、b，计算(x2,y2)=aG + bQ_A

2、计算：
```
r1 = x2 mod n
b1 = b^(-1) mod n
e1 = r1 * a * b1 mod n
s1 = r1 * b1 mod n
```
(r1,s1)即为伪造的签名。
