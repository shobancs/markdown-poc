# How to Document your software faster?

[Make a README] (https://www.makeareadme.com/) is a utility to build software documentation easy.
## Prerequisite
Vist noodejs installation [instructions] (https://nodejs.org/en/download/) for your specific OS.

```bash
$ npm install --save-dev marked
```


## To compile the markdown to HTML and write it to a new README.html file. Create a README.md with sample markdown content and  JS script file ```generateReadMe.js```.


```javascript
var marked = require('marked');
var fs = require('fs');

var readMe = fs.readFileSync('README.md', 'utf-8');
var markdownReadMe = marked(readMe);

fs.writeFileSync('./site/README.html', markdownReadMe);
```

## Create a index.html and add the following HTML object where the README.md content should be displayed
```html
<object data="README.html" type="text/html"></object>
```

## Then run this on the command line to make it happen:
```bash
$ node path/to/generateReadMe.js
```