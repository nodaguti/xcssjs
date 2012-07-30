XCSSjs
======

※引数の名前などは, https://developer.mozilla.org/en/CSS/-moz-linear-gradient に準拠しています.

What's the difference from the original one?
-----

* グラデーション（linear-gradient）のサポートの強化
 
  * 過去のすべての文法をサポート. どの形式で書かれていても自動で変換します. （文法の詳細は[History of the syntax](https://developer.mozilla.org/en/CSS/-moz-linear-gradient#History_of_the_syntax)を参照）
  
    * 以下の文法を実装しているブラウザーに対応しています. "to syntax", "from syntax", &lt;angle&gt;どれが使われていても, それぞれの文法に自動で変換します.

	    * 最新の "to syntax"（&lt;side-or-corner&gt;の前にtoをつける）
		* 古い "from syntax"（&lt;side-or-corner&gt;の前にtoをつけない）で, グラデーションの向きに &lt;angle&gt; を使用出来る文法
		* 古い "from syntax" で, グラデーションの向きに &lt;angle&gt; を使用できない文法
			* &lt;angle&gt;は特定の値（± 0/45/90/135/180/225/270/335/360deg）のみ対応

  * -webkit-gradientへの変換を完全サポート. Safari用のコードを書かなくても自動で変換します.
  
    * "to syntax", "from syntax" どちらで書かれた場合にも対応.
	* &lt;side-or-corner&gt;のすべてのキーワードの組み合わせに対応.
	* &lt;angle&gt;は特定の値のみ対応
	
	  * ± 0/45/90/135/180/225/270/335/360deg に対応しています.
	  
	* 第一引数を省略した場合にも対応（デフォルト値の top を指定した場合と同じになる）
	* &lt;color-step&gt;については, 必ず&lt;percentage&gt;による位置の指定を伴う必要があります. &lt;length&gt;による指定には対応していません.
	
  * SVGへの変換を完全サポート.
  
    * "to syntax", "from syntax" どちらで書かれた場合にも対応.
	* &lt;side-or-corner&gt;については, top/bottom/left/rightのみ対応.（left bottomなどの斜めのグラデーションには未対応）
	* &lt;angle&gt;は特定の値のみ対応.
	
	  * ± 0/90/180/270/360deg に対応しています.
	  
	* 第一引数を省略した場合にも対応.
	* &lt;color-step&gt;については, &lt;percentage&gt;による位置指定の他, 指定を省略した場合についても部分的に対応しています. なお, &lt;length&gt;による指定には対応していません.
	
	  * すべての&lt;color-step&gt;について位置の指定を省略した場合のみ対応しています. 部分的に省略した場合については仕様と挙動が異なります.
	  
* 対応プロパティを追加

  * user-select, appearance プロパティに対応しました.
  
ToDo
-----
* radial-gradientへの対応
* &lt;angle&gt;のサポートのさらなる充実
* &lt;color-step&gt;中で位置指定を省略した場合のフルサポート