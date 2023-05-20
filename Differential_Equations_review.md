---
layout: post
title: "My First Post"
date: 2023-05-18
---

# Differential Review

<!-- ## 我是sbbfx -->

## 椭圆型方程（17分）

$$ -(U_{xx}+U_{yy}) = f_{x,y} \tag{1}
$$

### 五点差分格式



□网格差分:


$$ - \frac{ {U_{k+1,j}} - {2U_{k,j}} + {U_{k-1,j}}} {h^2_x} - \frac{ {U_{k,j+1}} - {2U_{k,j}} + {U_{l,j-1}}} {h^2_y} = f_{k,j} \tag{2}
$$

假设$h_x = h_y = h$:

$$ \frac{4U_{k,j} - U_{k+1,j} -U_{k+1,j} - U_{k,j+1} -U_{k,j-1}}{h^2} = f_{k,j} \tag{3}
$$

### 九点差分格式（2选1）


◇网格查分:

假设$h_x = h_y = h$:

$$ \frac{4U_{k,j} - U_{k+1,j+1} -U_{k-1,j+1} - U_{k+1,j-1} -U_{k-1,j-1}}{2h^2} = f_{k,j} \tag{4}
$$

九点差分：
$$ \frac{2}{3} \cdot (3) + \frac{1}{3} \cdot (4) = f_{k,j} \tag{5}$$

### Fourier稳定性分析

五点差分：
令$ \lambda^k \cdot e^{i(\alpha k + \beta j)} = U^k_j$, 带入（3）,其中$f_{i,j} = 0$, 得到:

$$ λ^k e^{i(αk+βj)} = \frac{1}{4} \cdot (λ^k e^{i(α(k+1)+βj)} + λ^k e^{i(α(k-1)+βj)} + λ^k e^{i(αk+β(j+1))} + λ^k e^{i(αk+β(j-1))}) \tag{6}
$$

化简：

$$ λ = \frac{1}{4}(e^{i\alpha} + e^{-i\alpha} + e^{i\beta} + e^{-i\beta}) \tag{7}
$$

继续：

$$ λ = \cos(α) + \cos(β) \tag{8}
$$

结果：

$|λ|<2$ 时，格式稳定。


### 极值原理（离散型）（五点差分格式为例）

对于内部网格点：
$$U_{k,j} = \text{min or max} \implies U_{k \pm 1,j} < U_{k,j} \quad \text{and} \quad U_{k,j \pm 1} < U_{k,j} \quad (\text{for minimum}) \tag{8}
$$

$$U_{k,j} = \text{min or max} \implies U_{k \pm 1,j} > U_{k,j} \quad \text{and} \quad U_{k,j \pm 1} > U_{k,j} \quad (\text{for maximum}) \tag{9}
$$

对于边界网格点：
$$ U_{i,j} = \text{min or max} \implies U_{i\pm1,j} < U_{i,j} \quad (\text{for minimum}) \tag{11}
$$

$$ U_{i,j} = \text{min or max} \implies U_{i\pm1,j} > U_{i,j} \quad (\text{for maximum}) \tag{12}
$$

### 证明极值在边界上或者恒为常数


## 热传导方程（33分）

### 一维

$$ U_t = a \cdot U_{xx} \tag{1}
$$

#### 古典显格式

$$ \frac{U^{k+1}_{j} - U^{k}_{j}}{\tau} = a \cdot \frac{U^{k}_{j+1} - 2U^{k}_{j} +U^{k}_{j-1}}{h^2_x} \tag{2}
$$

令:

$$ r = \frac{a \cdot \tau}{h^2_x} \tag{3}
$$

整理得：

$$ U^{k+1}_{j} = r \cdot U^{k}_{j+1} +(1 - 2r) \cdot U^{k}_{j} + r \cdot U^{k}_{j-1} \tag{4}
$$

#### 古典隐格式

$$ \frac{U^{k+1}_{j} - U^{k}_{j}}{\tau} = a \cdot \frac{U^{k+1}_{j+1} - 2U^{k+1}_{j} +U^{k+1}_{j-1}}{h^2_x} \tag{5}
$$

令:

$$ r = \frac{a \cdot \tau}{h^2_x} \tag{6}
$$

整理得：

$$ U^{k}_{j} = -r \cdot U^{k+1}_{j+1} +(1 + 2r) \cdot U^{k+1}_{j} - r \cdot U^{k+1}_{j-1} \tag{7}
$$

#### CN格式（3选1）

$$ \frac{U^{k+1}_{j} - U^{k}_{j}}{\tau} = \frac{a}{2} \cdot (\frac{U^{k}_{j+1} - 2U^{k}_{j} +U^{k}_{j-1}}{h^2_x} + \frac{U^{k+1}_{j+1} - 2U^{k+1}_{j} +U^{k+1}_{j-1}}{h^2_x}) \tag{2}
$$

令:

$$ r = \frac{a \cdot \tau}{h^2_x} \tag{6}
$$

整理得：

#### Fourier稳定性分析

### 二维
#### PR格式
#### LOD格式
#### 稳定性分析（差分算子）

### 三维
#### LOD格式
#### 稳定性分析（差分算子）


## 双曲型方程（30分）

### 一维
#### 迎风格式
#### LW格式
#### LF格式
#### B-W格式
#### Fourier稳定性分析

### 二维
#### 迎风格式
#### 显式中心差分格式（$L^{\infty}$稳定）
#### 最大值定理条件
#### Fourier稳定性分析


## 波动型方程（20分）

### 一维
#### 古典显格式
#### 古典隐格式
#### 加权格式
#### 稳定性分析

### 二维
#### ADI格式