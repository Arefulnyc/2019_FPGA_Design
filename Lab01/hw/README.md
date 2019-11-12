Homework 1
=============================

# 繳交時間

**2019/10/7(Mon.) 18:59**

## Program 1 - 使用板子上的 RGB LED 實現路口交通號誌 (90%)

### 作業說明

使用兩顆 RGB LED ，分別代表一個路口的兩個燈號

作業需求：

1. 兩個路口的黃燈長(t1)皆為 **1 sec** ，綠燈長(t2)皆為 **5 sec** ，兩者皆為紅燈的時間長(t3)為 **1 sec** _(1 sec 不必是實際準確的一秒，可直接使用 Lab 提供的除頻器_

2. 一個路口為黃燈或是綠燈時，另一個一定為紅燈

#### Hint : RGB LED 的控制

一顆 RGB LED 由三個 Bit 控制，分別為 R G B；

對應到 xdc file 上的控制腳位為 `RGB LEDs` 那欄。

[如何製造黃燈](https://zh.wikipedia.org/wiki/%E4%B8%89%E5%8E%9F%E8%89%B2%E5%85%89%E6%A8%A1%E5%BC%8F)

## Bonus (20%)

### 作業說明

加入 Switches 和 Buttons 來調整 Program 1 的三種時間長。

作業需求：

1. Switch 為 `00` 時 ，紅綠燈正常運作。

2. Switch 為 `01` 時 ，使用 Buttons 調整黃燈長(t1)。

3. Switch 為 `10` 時 ，使用 Buttons 調整綠燈長(t2)。

4. Switch 為 `11` 時 ，使用 Buttons 調整兩者重疊的紅燈長(t3)。

5. 用 4-bit LED 以二進位顯示秒數。

## Bonus 2 (20%)

畫出系統設計圖 (非合成後的電路圖)。

## Problems (10%)

1. 為什麼要加入 blinky.xdc 這個 Constraint ?

> [Hint](https://www.xilinx.com/support/documentation/sw_manuals/xilinx2018_1/ug903-vivado-using-constraints.pdf)、 [Hint too](https://forums.xilinx.com/t5/Synthesis/Clock-Dividers-XDC-definition-best-practice/td-p/709540)

2. 承上題，若沒有加入這個 Constraint，可能會發生什麼事?

# 作業成績

| 組別 | 分數 | 備註 |
|------|------|-----|
|1|140||
|2|85|功能正常但xdc中沒有連接的腳位不需要連接(35-37行)。Combinational Circuit中case中的訊號需要在所有case中都描述行為(包含default)，如LED.v之164,166行需要加上led4,5之rgb描述。Problems1並不是產生訊號，而是告知工具我們在divider中有自行產生一個的clk，使工具在分析clk時有使用者定義的數值。|
|3|120|Bouns2不完整。檔案少附，建議在Bonus中加上調整的上限。Problem1還有包含告知工具我們在divider中有自行產生一個的clk，使工具在分析clk時有使用者定義的數值。|
|4|115|功能正常但Combinational Circuit中case中的訊號需要在所有case中都描述行為(包含default)，如controller.v之13,19,25,32行需要加上control_y,g,r_out之描述。Bouns2不完整。Problem1是告知工具我們在divider中有自行產生一個的clk，使工具在分析clk時有使用者定義的數值。|
|5|130|功能正常但通常我們在verilog的always block中不會使用posedge來偵測按鈕是否按下(因為系統無法預期外部btn的頻率，無法在xdc加上constrain，導致implementation時btn reg扇出數過大以及clk的問題出現)，通常還是以system clk來判斷是否有觸發按鈕。Bouns2不完整。|
|6|90|功能正常但Combinational Circuit中case中的訊號需要在所有case中都描述行為(包含default)，如LED.v之case中的描述，並且請勿將判斷條件的值於該描述中更動，如LED.v之39行的判斷以及169行的更動，很容易造成電路競爭行為。Problem1還有包含告知工具我們在divider中有自行產生一個的clk，使工具在分析clk時有使用者定義的數值。|
|7|100|功能正常但Bonus之top.v之24行port最後多加,，以及未在top.v中連接出來(btn,led)，因此不給予分數。|
|8|115|功能正常但top.v之17行的module名字與12行output重複。RGB_LED.v中的timer reg並未於rst時給予初始值。|
|9|125|功能正常但Combinational Circuit中case中的訊號需要在所有case中都描述行為(包含default)，如LED_RGB.v之case中的描述需要加上led4,5之rgb描述。|
