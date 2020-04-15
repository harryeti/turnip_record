## 大头菜价格源码整理：

### 综合

大头菜每周类型分为：波动型、递减型、三期型、四期型。

每周日可以买大头菜，买到的大头菜的价格为这周的基础价；

每周一～周六可以卖大头菜，上下午一共12期

### 波动性：

#### 概述：

每周出现3个波峰和波谷，波谷在 基础价×\[0.5\~0.8] 之间波动，波峰在 基础价×\[0.9~1.4]之间波动。

#### 详情：

- 每周前\[0\~6]期出现第一个波峰，每日价格为 基础价×\[0.9~1.4] 的随机数
- 之后出现2或3期的波谷，波谷第一天价格为 基础价×\[0.8\~0.6] 的随机数，后面为上一期比例的基础上再减\[0.04~0.1]
- 之后出现\[1\~7]期的波峰，每日价格为 基础价×\[0.9~1.4] 的随机数
- 之后出现3或2期的波谷
- 剩下的几天出现波峰

#### 下一周概率：

20%波动，30%三期，15%递减，35%四期

### 递减型：

#### 概述

每周第一期最高，之后一直递减

#### 详情

- 第一期价格为 基础价×\[0.85~0.9] 的随机数
- 之后每期价格为上一期比例的基础上再减\[0.03~0.05]

#### 下一周概率

25%波动，45%三期，5%递减，25%四期

### 三期型：

#### 概述

前几天低价，后突然上涨，最高可出现6倍价格

#### 详情

前几天的价格和递减型类似

- 第一期价格为 基础价×\[0.85~0.9] 的随机数
- 之后每期价格为上一期比例的基础上再减\[0.03~0.05]

在第[2,8]期开始突然上涨，设第一次上涨期数为n

- 第n期：基础价×\[0.9~1.4] 的随机数
- 第n+1期：基础价×\[1.4~2.0] 的随机数
- 第n+2期：基础价×\[2.0~6.0] 的随机数
- 第n+3期：基础价×\[1.4~2.0] 的随机数
- 第n+4期：基础价×\[0.9~1.4] 的随机数
- 在之后为 基础价×\[0.4~0.9] 的随机数

#### 下一周概率

50%波动，5%三期，20%递减，25%四期

### 四期型：

#### 概述

前几天超低价，后突然上涨，最高可出现2倍价格

#### 详情

- 第一期价格为 基础价×\[0.4~0.9] 的随机数
- 之后每期价格为上一期比例的基础上再减\[0.03~0.05]

在第[0,8]期开始突然上涨，设第一次上涨期数为n

- 第n期：基础价×\[0.9~1.4] 的随机数
- 第n+1期：基础价×\[0.9~1.4] 的随机数

设r=\[1.4~2.0] 的随机数

- 第n+2期：基础价×\[1.4~r] 的随机数
- 第n+3期：基础价×r 的随机数
- 第n+4期：基础价×\[1.4~r] 的随机数
- 在之后为 基础价×\[0.4\~0.9] 的随机数，再之后每期价格为上一期比例的基础上再减\[0.03~0.05]

#### 下一周概率

45%波动，25%三期，15%递减，15%四期

## 大头菜价格列表记录

### 无人岛

|时间|购入价|周一上|周一下|周二上|周二下|周三上|周三下|周四上|周四下|周五上|周五下|周六上|周六下|
|----|------|-----|-----|------|-----|-----|------|------|-----|-----|------|-----|------|
|20200412-20200418|90|-----|-----|65|61|56|------|------|-----|-----|------|-----|------|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
