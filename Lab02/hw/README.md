Homework 2
====================

## Program 1 - 使用 PWM 產生彩虹七色 (50%)

### 繳交期限

10/14(Mon.) 18:59

### 作業說明

使用一顆 RGB LED ，透過給予不同的 R、G、B time 來產生彩虹七色。

### 作業需求

1. 七種顏色不必淡出淡入，可以分段產生。
> ex : 紅色亮2秒後換橙色，橙色亮2秒後換黃色，依此類推。

2. **必須自己建立IP，使用Block Design完成作業**

3. 上傳作業時須連 IP 資料夾一起上傳。*(參照Lab2-1)*

### Hint

1. [各色RGB值參考](https://microdnd.pixnet.net/blog/post/103334755-%5B%E7%A8%8B%E5%BC%8F%5D-%E5%90%84%E9%A1%8F%E8%89%B2rgb%E5%80%BC%E5%8F%83%E8%80%83%E8%A1%A8)

2. System Block 可以參考 Lab 2-1 *(i.e.改寫其中一個Block即可)*，

## Program 2 - 使用單色 LED 實作呼吸燈 (50%)

### 作業說明

使用板子右下角的單色 LED ，實作一顆呼吸燈。

### 作業需求

1. 使用一顆 LED 實作產生漸強漸弱的呼吸燈即可。

2. 呼吸燈長[這樣](https://www.youtube.com/watch?v=Z6tbQ0HNmag)

3. 可選擇使用IP -> Block Design的方式，也可以純寫 Verilog code 來實作。

## Bonus - 電競 RGB 呼吸燈 (20%)

### 作業說明

科技日新月異，電子競技這項運動項目逐漸崛起，而提到電競就不得不提到附有 RGB 色燈的各項電腦周邊，如：滑鼠、鍵盤、風扇、甚至水冷系統，任何你想的到的電競相關的產品都會有 RGB 燈在上面。

請綜合上面兩題的概念，使用 RGB LED 實作呼吸燈。

### 作業需求

1. 使用一顆 RGB LED 即可。

2. 呼吸燈顏色和第一題一樣需按照彩虹七色的順序來顯示。

# 作業成績

| 組別 | 分數 | 備註 |
|------|------|-----|
|1|115|Program1之RGB_LED.v的Sequential Circuit內對register的存取應該要使用<=(44行always block)。|
|2|100|Program1之所有IP都需要ooc(有clk)，並且需要定義clk_div產生的clk訊號(如Lab01之blinky.xdc)。Program2,3少附腳位xdc檔案。|
|3|115|Combinational Circuit中case中的訊號需要在所有case中都描述行為(包含default)，如Bonus的state_a.v之52行需要加上n_state之描述。|
|4|105|Program1,2,Bonus之PWM_ooc的除頻電路訊號名稱有誤。腳位xdc中沒有連接的腳位不需要連接。Bonus中led_pwm.v中的cstate_color reg並未於rst時給予初始值。|
|5|110|腳位xdc檔案只有一份，但是每題的output都不一致。Program2之LED.v的output led未定義[3:1]之行為。|
|6|85|無法找到腳位xdc檔案，以及未附Block degisn圖。Program1之RWM_Decoder.v與Program2之HW_LED_Decoder.v的Sequential Circuit內對register的存取應該要使用<=(1:30-75行,2:51行)。|
|7|95|無法找到腳位xdc檔案。|
|8|120||
|9|115|Program1,Bonus之divider_ooc的除頻電路訊號名稱有誤。Bonus之PWM_led.v的Combinational Circuit中應為blocking寫法(23,25行應為=)。|
