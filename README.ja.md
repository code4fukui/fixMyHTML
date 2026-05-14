# fixMyHTML

HTML内の一般的な問題を、全角文字の半角変換や埋め込みJavaScriptの再フォーマットによって修正する軽量なESモジュールです。

## 機能

- **文字変換:** 全角の英数字や記号（例: `＜`, `＞`）を標準の半角文字に変換します。
- **JavaScriptの整形:** [esreform](https://github.com/code4fukui/esreform/)を使用して、`<script>`タグ内のJavaScriptコードを自動的に再フォーマットし、きれいに整形します。
- **エラー耐性:** `<script>`タグ内のJavaScriptに構文エラーが含まれている場合でも、エラーをスローすることなくそのまま維持されます。
- **ESモジュール:** URLインポートを利用して、ブラウザ、Deno、その他のモダンなJavaScript環境ですぐに使用できます。

## 使い方

モジュールをインポートし、HTML文字列を`fixMyHTML`関数に渡します。

```javascript
import { fixMyHTML } from "https://code4fukui.github.io/fixMyHTML/fixMyHTML.js";

// 全角文字と整形されていないJavaScriptを含む例
const brokenHTML = '＜html＞<script>if(true)alert(1)</script>';

const fixedHTML = fixMyHTML(brokenHTML);

console.log(fixedHTML);
/*
出力:
<html><script>
if (true) {
  alert(1);
}
</script>
*/
```

## 依存関係

- [esreform](https://github.com/code4fukui/esreform/) - JavaScriptの整形用。
- [mojikiban/ZenkakuAlpha](https://github.com/code4fukui/mojikiban) - 全角から半角への文字変換用。

## 関連

- [fixmyjs](https://github.com/code4fukui/fixmyjs/) - JavaScriptの修正に特化した類似ツール。

## ライセンス

MIT License - 詳細は[LICENSE](LICENSE)を参照してください。
