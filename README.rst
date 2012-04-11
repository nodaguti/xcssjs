XCSSjs
======

※引数の名前などは, https://developer.mozilla.org/en/CSS/-moz-linear-gradient に準拠しています.

What's different from original one?
-----

- グラデーション（linear-gradient）のサポートの強化

  - -webkit-gradientへの変換をサポート. Safari用のコードを書かなくても自動で変換します.
  
    - 最新の仕様（<side-or-corner>の前に, toをつける）にも対応. もちろん付けなくても大丈夫です.
	- <side-or-corner>の部分については, すべてのキーワードの組み合わせに対応.
	- <angle>には, 特定の値のみ対応
	
	  - ± 0/45/90/135/180/225/270/335/360deg に対応しています.
	  
	- 第一引数を省略した場合にも対応（デフォルト値の top を指定した場合と同じになる）
	- <color-step>については, 必ず<percentage>による位置の指定を伴う必要があります. <length>による指定には対応していません.
	
  - SVGへの変換をサポート.
  
    - 最新の仕様（<side-or-corner>の前に, toをつける）にも対応.
	- <side-or-corner>については, top/bottom/left/rightのみ対応.
	- <angle>については, 特定の値のみ対応.
	
	  - ± 0/90/180/270/360deg に対応しています.
	  
	- 第一引数を省略した場合にも対応.
	- <color-step>については, <percentage>による位置指定の他, 指定を省略した場合についても部分的に対応しています. なお, <length>による指定には対応していません.
	
	  - すべての<color-step>について位置の指定を省略した場合のみ対応しています. 部分的に省略した場合については仕様と挙動が異なります.
	  
- 対応プロパティを追加

  - user-select, appearance プロパティに対応しました.
  
ToDo
-----
- radial-gradientへの対応
- <side-or-corner>の前にtoを付ける形式と付けない形式の相互変換のサポート
- <angle>のサポートのさらなる充実
- <color-step>中で位置指定を省略した場合のフルサポート