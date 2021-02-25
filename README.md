## CSSファイルの構成について

ファイルは下記のようになっている。

| css         | 内容                  |
| ----------- | --------------------- |
| xxx.css     | 使用される圧縮版CSSの |
| xxx_raw.css | 圧縮前CSS             |

### 編集の流れ

1. xxx_raw.cssを編集
2. [CSSの圧縮を行う](http://e-optimize.jp/services/csstidy/css_optimiser.php)
   1. Code Layout
      1. 圧縮率: 最高(改行なし)
   1. Options
      1. CSSの内容を保護する
      1. colorの値を簡略化する
      1. font-weightを数値にする
      1. 不要なバックスラッシュを削除
      1. 最適化の結果を保存する
3. 圧縮結果をxxx.cssに反映する
4. Commit-Push

## グローバルナビ

レスポンシブ対応のため、CSSとjavascriptが連携している。

フッターのコード

```html
<!-- グローバルグローバルナビ-->
<script type="text/javascript">
    $(function () {
        $("#toggle").click(function () {
            $("#menu").slideToggle();
            return false;
        });
        $(window).resize(function () {
            var win = $(window).width();
            var p = 680;
            if (win > p) {
                $("#menu").show();
            } else {
                $("#menu").hide();
            }
        });
    });
</script>
```

のうち

```javascript
var p = 680;
```

がCSSの

```css
@media only screen and (max-width: 680px) {
    ...
}
```

の「max-width」指定pxと同値とする必要がある。

