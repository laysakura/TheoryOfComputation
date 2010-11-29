差し込み印刷をするためのスタイルファイルです．

使用例として，模擬試験の個人票を同梱しました。

  個人票の形式を記述したものが    kohyou.tex
  差し込みデータファイルが        sasikomi.csv（ CSV形式 ）

使用法は簡単で
    step 1:  \OpenDataFile{9}{sasikomi.dta}
      により，差し込みデータファイルを指定します．
      そのさい，項目数を指定します．
      ついで
    step 2:  \Sasikomi{kohyou.tex}
      として書式ファイルを指定します．
具体的には
    sampleC.tex （ csv形式）
をご覧ください．
