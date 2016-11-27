demonstration of strict-mode issue with proxyquire:
* `proxyquire-plugin` injects an IIFE at the start of scripts that `require("proxyquire")`.
* the injected IIFE is inserted before any `"use strict"` statement in the script,
[invalidating strict-mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode).
* to work around this behaviour, the script can for example be encapsulated
in a strict-mode function, e.g. an IIFE or a describe block.

the demo is based on the differing interpretation of "this" in an unbound function:
* `undefined` in strict mode
* `window` in non-strict mode (in the browser)

# USAGE
either [view the tests here in your browser](https://cdn.rawgit.com/smcatala/proxyquire-strict-mode-issue/v1.0.0/spec/web/index.html),

or fork this repository and run the following commands:
```bash
npm install
npm test
```

# LICENSE
The MIT License (MIT)
Copyright (c) 2016 Stéphane M. Catala

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.