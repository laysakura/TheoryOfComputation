emathBt.sty は
　　本文と傍注の間に縦罫線を引く
ことを主目的としています。
Bt は
　　Bou Tyuu
　　^   ^
のつもりです。
emath を冠していますが，emathの他のファイルとはまったく独立です。
（現時点では，の話で将来的にはわかりません。）

罫線の幅は
　　\marginparseprule
で決まり，デフォルト値は 0.4pt となっています。

縦罫線を引くには，
　　\usepackage{emathBt}
とするだけです。実例を ex1.tex とします。

脚注と同じく，傍注にも注番号をつけるコマンド
　　\boutyuu
を\marginpar に変えて用いることが出来ます。---> ex2.tex

章，節などの部分の罫線を切るには，その部分を
　　nomarginparseprule環境
内に記述します。 ---> ex3.tex
ただし，この機能は color.sty を必要とします。

制限事項
1. 縦組には対応していません。
2. twocolumn, \reversemarginpar には対応していません。
