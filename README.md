## CSSファイルの構成について

ファイルは下記のようになっている。

- xxx.css: 使用される圧縮版CSSの
- xxx_raw.css: 圧縮前CSS

### 編集の流れ

1. xxx_raw.cssを編集
2. [CSSの圧縮を行う](http://e-optimize.jp/services/csstidy/css_optimiser.php)
3. 圧縮結果をxxx.cssに反映する
4. Commit-Push

