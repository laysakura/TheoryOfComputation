emathFx.styは，txfonts, pxfonts などのフォントの一部を
つまみ食いするためのファイルです。

当然，それらのフォントがインストールしてあることが前提です。

現時点で用意されているオプションは
tx : txfonts
px : pxfonts
eu : euler
xy : Xy-pic パッケージ
abx: mathabx fonts
の5種類です。

角藤氏の「標準インストール」をしていれば，
   tx, px, eu, abx
はインストールされますが，Xy-pic パッケージは含まれていませんから，
これを使うためには
    CTAN:macros/generic/diagrams/xypic/
からファイルを取ってきて，その中のドキュメント
    Readme, Install
にしたがってインストールする必要があります。
