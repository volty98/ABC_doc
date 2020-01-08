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

### CMD

【機能】CMDする

【書式】CMD -arg1 [-arg2:param2]

【用例】
```
ABC>CMD -arg1 -arg2:param2
uhouho
ABC>
```

