XCSSjs
======

※引数の名前などは, https://developer.mozilla.org/en/CSS/-moz-linear-gradient に準拠しています.

What's the difference from the original one?
-----

* グラデーション（linear-gradient）のサポートの強化
 
  * 過去のすべての文法をサポート. どの形式で書かれていても自動で変換します. （文法の詳細は[History of the syntax](https://developer.mozilla.org/en/CSS/-moz-linear-gradient#History_of_the_syntax)を参照）

    * 以下の文法を実装しているブラウザーに対応しています. "to syntax", "from syntax", <angle>どれが使われていても, それぞれの文法に自動で変換します.

      * 最新の "to syntax"（<side-or-corner>の前にtoをつける）
      * 古い "from syntax"（<side-or-corner>の前にtoをつけない）で, グラデーションの向きに <angle> を使用出来る文法
      * 古い "from syntax" で, グラデーションの向きに <angle> を使用できない文法

        * <angle>は特定の値（± 0/45/90/135/180/225/270/335/360deg）のみ対応

  * -webkit-gradientへの変換を完全サポート. Safari用のコードを書かなくても自動で変換します.

    * "to syntax", "from syntax" どちらで書かれた場合にも対応.
    * <side-or-corner>のすべてのキーワードの組み合わせに対応.
    * <angle>は特定の値（ ± 0/45/90/135/180/225/270/335/360deg）のみ対応
    * 第一引数を省略した場合にも対応（デフォルト値の top を指定した場合と同じになる）
    * <color-step>については, 必ず<percentage>による位置の指定を伴う必要があります. <length>による指定には対応していません.
  
  * SVGへの変換を完全サポート.

    * "to syntax", "from syntax" どちらで書かれた場合にも対応.
    * <side-or-corner>については, top/bottom/left/rightのみ対応.（left bottomなどの斜めのグラデーションには未対応）
    * <angle>は特定の値（± 0/90/180/270/360deg ）のみ対応.
    * 第一引数を省略した場合にも対応.
    * <color-step>については, <percentage>による位置指定の他, 指定を省略した場合についても部分的に対応しています. なお, <length>による指定には対応していません.
  
      * すべての<color-step>について位置の指定を省略した場合のみ対応しています. 部分的に省略した場合については仕様と挙動が異なります.
    
* 対応プロパティを追加

  * user-select, appearance プロパティに対応しました.
  
ToDo
-----
* radial-gradientへの対応
* <angle>のサポートのさらなる充実
* <color-step>中で位置指定を省略した場合のフルサポート