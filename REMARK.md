# Using Remark

1.  Install deps: `yarn add remark-cli remark-html remark-preset-lint-markdown-style-guide unified remark-parse -D`

## Converting markdown readme.md to html

```js
// example.js -->
var fs = require("fs");
var unified = require("unified");
var markdown = require("remark-parse");
var html = require("remark-html");

unified()
  .use(markdown)
  .use(html)
  .process(fs.readFileSync("README.md"), function(err, file) {
    if (err) throw err;
    console.log(String(file));
  });
```

Then run `node example.js` where it reading `README.md`.
To save run `node example.js > README.html`. Css isnt right but this otherwise works.
