Homework 4
====

## 繳交時間
2019/11/4(Mon) 18:59

請將以下電路同整在一個 block design，並且每個 ip 都要上傳且都要有 ooc (IP 怎能沒有先合成過呢)，請勿只交 hdl code。

### Program 1.

設計一個排序電路，由 processor 輸入一串正整數將其排序後傳回。(數列長度固定)

#### 說明

1. 數字位元數自訂(最少4bit)

2. 數列長度自訂(最少8筆數字)

3. 需在作業說明中註明使用的排序法、定義的數字位元數、數列長度


### Program 2.

設計一個計算電路，由 processor 輸入運算子與運算元並回傳運算完的結果。(加, 減, 乘)

#### 說明

1. 資料寬度為8 bit

2. 需考慮有號數(正、負、overflow)


### Program 3.

設計 parity generator，輸入 32-bit 資料回傳其 parity bit (**禁止額外暫存器的使用 ex: counter**)。

### Program 4.

設計 [djb2](http://www.cse.yorku.ca/~oz/hash.html) 這個 hash function 的電路。

### Program 5.

設計 PWM controller。

#### 說明

1. 由 processor 端傳送 R、G、B 三組 PWM 值 (i.e. 色碼值)

2. 透過硬體解碼器驅動 RGB LED 發光

可參考 [Creating a Custom IP core using the IP Integrator ](https://reference.digilentinc.com/learn/programmable-logic/tutorials/zybo-creating-custom-ip-cores/start?redirect=1)。

### Block Diagram

![block_diagram](../images/block_diagram.jpg)
