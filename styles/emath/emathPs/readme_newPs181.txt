emathPs.sty (v 1.81 2010/05/02) にロードオプション
    remakefalse
    pdf
    PDF
を新設しました。

1) remakefalse
  emathPs.sty はデフォルトでは
  　　[remake] オプションがついている
  ものとしてあります（v 1.75 2010/03/07　以降）。
  remakefalse はそれを打ち消すもので，eps ファイルは更新されません。

以下は
　　dvipdfm(x) を用いる
というのが前提です。
以下のソースを 
　　dviout (or dvips) で見れない，見たらおかしい
などというクレームは「場外」です。

2) pdf
  2-1) remakefalse と併用するのが原則で（将来は単独使用も可能としたい），
    　　pdf が存在しない場合
    または
    　　pdf が eps より古い場合
    には，eps を pdf に変換します。
    （その際，xbb ファイルも作成/変更されます。）
  2-2) eps ではなく，pdf を読み込みます。

3) PDF
  remakefalse と併用する，というのは pdf オプションと同様です。
  pdf オプションでは，必要のある場合は eps --> pdf 変換をしますが，
  PDF オプションは，eps には目もくれず，pdf を読みに行きます。
  eps と pdf の比較などをしない分高速になりますが，
  eps が更新されていても古い pdf を読んでしまいます。
  eps を更新した場合は 
  　　pdf オプションで pdf も更新
  したうえで PDF オプションを用います。

注1. eps→pdf 変換は
        epstopdf
     を使用しています。
     これを拒否したい場合は，別途何らかの方法で pdf を作成しておけば，
     epstopdf は起動しません。

注2. ファイルのタイムスタンプ取得を perl の stat 関数で行っていますから，
　　perl との連携が必要です。

注3. EPSfilename=.....
    におけるファイル名指定を行う場合は，
    　　　拡張子 eps 
    を原則とします（pdf ではない）。
    ロードオプション pdf(PDF) をつけた場合は，
    　　　.....eps を ..... pdf
    と読み替えて pdf を読みにいきます。

注4. [remakefalse,pdf] オプションは，
　　個々の pszahyou(*)環境につけることも可能で，
　　その場合は，当該 pszahyou(*)環境のみに働きます。

注5. 文書全体には
　　　　\usepackage[remakefalse,pdf]{emathPs}
　　とした場合，
　　特定の pszahyou*環境に [remake,eps] オプションをつけると
　　当該 pszahyou(*)環境についてのみ
　　　　eps ファイルは更新され，
　　　　pdf ではなく eps が読み込まれます。
　　そのあとで remake,eps オプションを消去してタイプセットすれば，
　　pdf が作成（更新）され，pdf が読み込まれることになります。
　　　現時点では，[remake]オプションのみで同じ動作をしますが，
　　将来 pdf オプションが単独の意味を持つようになれば，
　　動作が変わってくる可能性があります。

注5' 文書全体には
　　　　\usepackage[remakefalse,PDF]{emathPs}
　　とした場合，
　　特定の pszahyou*環境に [remake,eps] オプションをつけると
　　当該 pszahyou(*)環境についてのみ
　　　　eps ファイルは更新され，
　　　　pdf ではなく eps が読み込まれます。
　　そのあとで remake,eps オプションを remake,pdf オプションに変更して
　　タイプセットすれば，pdf が作成（更新）され，
　　pdf が読み込まれることになります。
　　　さらに，remake,pdf オプションも消せば，全体のオプション
　　　　remakefalse,PDF
　　が有効となります。

注6. dvipdfmx.def [1999/02/16 v3.0i Driver-dependant file (DPC,SPQR)]
　　にはバグがあり，図が半角空白分だけ右にずれます。
　　dvipdfmx.def を write18 で検索すると
　　    \immediate\write18{extractbb \Gin@base\Gin@ext}
　　という行が見つかりますが，その行末に % 1文字を付加し
　　    \immediate\write18{extractbb \Gin@base\Gin@ext}%
　　と修正することで，半角空白の混入を回避することが出来ます。

注7. xbb ファイルは自動的に作成されます（dvipdfmx.def の機能）。
　　（あらかじめ用意する必要はありません。）

注8. pdf オプションは，perl との連携機能に依存しますから，
　　platex に対する -shell-escape オプションの付加が必須です。

注9. 今回の改訂仕様は暫定的なものであり，
　　次の修正パックまでには大きな変更がなされる可能性がありますから，
　　ご承知おき願います。

今回の emathPs.sty の改訂は他のスタイルファイルにも影響しますので
    emath.sty v2.27
    emathPl.sty v0.23
    emathPp.sty v0.87
    emathPh.sty v3.84
    emathPk.sty v1.20
も同梱してあります。
また，サンプルリスト
    newPs181.tex
も同梱します。
