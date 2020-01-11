# Airio-Base Console ABC コマンドリファレンス

## コマンド書式
**command** [-arg1[:param1]] [-arg2[:param2]] [-arg3[:param3]]

### 例1：ledポート1に0(Low)を出力
```
led -num:1 -out:0
```
### 例2：Airio-Baseをソフトリセット
```
reset
```

## コマンド一覧
|  コマンド | 引数1 | 引数2 | 引数3 | 機能 |
| :---- | :---- | :---- | :---- | :---- |
| help |  |  |  | コマンド一覧表示 |
| rem | -label:[LB] | | | コメント行、[LB]でラベル定義 |
| led | -num:[1/2] | -out:[1/0] | | led(1/2)の点灯(0)/消灯(1) |
| sd_en | -pwr:[1/0] | | | SDカード電源ON(1)/OFF(0) |
| sdopen | -file:[FL] | -mode:[RW] | | SDカード内のファイルオープン |
| sdclose | | | | オープンしたファイルのクローズ |
| sdfgets | | | | オープンしたファイル内容の表示 |
| reset | | | | ソフトリセット |
| i2cw | -addr:[A] | -cmd:[D] | -stop | I2C ライトコマンド |
| i2cr | -addr:[A] | -len:[L] | | I2C リードコマンド |
| pwm | -port:[P] | -hz:[H] | -duty:[D] | PWMポート出力 |
| set | -name:[N] | -type:[T] | -value:[V] | 変数の設定 |

## コマンドリファレンス
### help
【機能】コマンド一覧を表示する

【書式】help

【用例】
```
ABC>help
help 
rem
led
sd_en
sdopen
sdclose
sdfgets
reset
i2cw
i2cr
pwm
set
ABC>
```

### rem

【機能】コメント行、及びジャンプ命令用のラベルを定義。主にスクリプト実行時で利用

【書式】
- rem _text_
- rem -label:"_param1_"

【用例】
```
ABC>rem LED_ON
ABC>led -num:1 -out:0
ABC>
```
以下は、スクリプト実行用テキストファイル内の記述
```
rem -label:"SSD1306_INIT"
i2cw -addr:78 -cmd:80AE00A83F00D300804080A180C800DA120081FF
i2cw -addr:78 -cmd:80A480A600D580002010
i2cw -addr:78 -cmd:002200070021000F008D1480AF
rem
led -num:2 -out:0
```

### led

【機能】ledの点灯制御

【書式】led -num:_param1_ -out:_param2_

【用例】
```
ABC>led -num:1 -out:0
ABC>led -num:1 -out:1
ABC>led -num:2 -out:0
ABC>led -num:2 -out:1
ABC>
```

