考査用紙の書式で，Ｂ４横の多段組をするためのスタイルファイルです．

  二段組については，twocolumn オプションを用いるのが簡単です．
pLaTeX2e になってから，版面が狭くなっていますので，
その点を修正したのが同梱の sample0.tex です．

  さて，三段・四段なりますと，multicol パッケージを用いる方法がありますが，
数学の考査のように余白が多い場合は調整が面倒です．
ということで，
    三段組用のスタイル b4yoko3.sty
    四段組用のスタイル b4yoko4.sty
を作ってみました．

  使用法の大雑把な説明をします．

step 1. 考査のタイトルを  \testname の引数として記述します．
  （例） \testname{\ 1学年『数学I』二学期中間考査\ \ 1998.10.22(木)\ }

step 2. 一枚のシートの内容を sheet 環境内に記述します．
    step 2-1 一段目の内容を column 環境内に記述します．
             この環境は，実質 enumerate 環境ですから，
             大問のはじめに \item を記述します．
    step 2-2 二段目を column 環境内に記述します．
    step 2-3 三段目です．

すなわち

    \begin{sheet}
        \begin{column} 
            \item aaa 
        \end{column}
        \begin{column} 
            \item bbb
        \end{column}
        \begin{column} 
            \item ccc 
        \end{column}
    \end{sheet}

という構成になります．
  なお，１つの列(column)に複数の問題を入れるときは，その間隔を空けるのに
  	(1) \vspace{5cm} などと空白の長さを指定する方法
と
	(2) \vfill で均等割する方法
の２つの方法があります．

詳しくは，以下のサンプルファイルをご覧ください．

    sample0.tex twocolumn オプションを用いた二段組のサンプル

    sample1.tex 三段組のサンプル
    sample2.tex                 （複数枚）
    sample3.tex                 （両面印刷）
    sample4.tex 三段組の実例
    sample5.tex                 （解答を裏面に印刷する実例）

    sample6.tex 四段組のサンプル

    sample7.tex 縦間隔を \vfill で均等割
