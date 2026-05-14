# fixMyHTML

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A lightweight ES module to fix common issues in HTML by converting full-width characters and reformatting embedded JavaScript.

## Features

- **Character Conversion:** Converts full-width alphanumeric characters and symbols (e.g., `＜`, `＞`) to their standard half-width equivalents.
- **JavaScript Formatting:** Automatically reformats and beautifies JavaScript code inside `<script>` tags using [esreform](https://github.com/code4fukui/esreform/).
- **Error-Tolerant:** If JavaScript inside a script tag contains a syntax error, it is left as-is without throwing an error.
- **ES Module:** Ready to use in browsers, Deno, and other modern JavaScript environments via URL import.

## Usage

Import the module and pass your HTML string to the `fixMyHTML` function.

```javascript
import { fixMyHTML } from "https://code4fukui.github.io/fixMyHTML/fixMyHTML.js";

// Example with full-width characters and unformatted JavaScript
const brokenHTML = '＜html＞<script>if(true)alert(1)</script>';

const fixedHTML = fixMyHTML(brokenHTML);

console.log(fixedHTML);
/*
Output:
<html><script>
if (true) {
  alert(1);
}
</script>
*/
```

## Dependencies

- [esreform](https://github.com/code4fukui/esreform/) - For JavaScript formatting.
- [mojikiban/ZenkakuAlpha](https://github.com/code4fukui/mojikiban) - For full-width to half-width character conversion.

## Related

- [fixmyjs](https://github.com/code4fukui/fixmyjs/) - A similar tool focused exclusively on fixing JavaScript.

## License

MIT License - see [LICENSE](LICENSE).