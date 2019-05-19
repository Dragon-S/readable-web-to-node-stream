[![Build Status](https://travis-ci.org/Borewit/readable-web-to-node-stream.svg?branch=master)](https://travis-ci.org/Borewit/readable-web-to-node-stream)
[![NPM version](https://badge.fury.io/js/readable-web-to-node-stream.svg)](https://npmjs.org/package/readable-web-to-node-stream)
[![npm downloads](http://img.shields.io/npm/dm/readable-web-to-node-stream.svg)](https://npmcharts.com/compare/readable-web-to-node-stream)
[![dependencies Status](https://david-dm.org/Borewit/readable-web-to-node-stream/status.svg)](https://david-dm.org/Borewit/readable-web-to-node-stream)
[![Known Vulnerabilities](https://snyk.io/test/github/Borewit/readable-web-to-node-stream/badge.svg?targetFile=package.json)](https://snyk.io/test/github/Borewit/readable-web-to-node-stream?targetFile=package.json)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/b48f9601e0984734b1962913f70432a6)](https://www.codacy.com/app/Borewit/readable-web-to-node-stream?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Borewit/readable-web-to-node-stream&amp;utm_campaign=Badge_Grade)
[![Coverage Status](https://coveralls.io/repos/github/Borewit/readable-web-to-node-stream/badge.svg?branch=master)](https://coveralls.io/github/Borewit/readable-web-to-node-stream?branch=master)
[![Minified size](https://badgen.net/bundlephobia/min/readable-web-to-node-stream)](https://bundlephobia.com/result?p=readable-web-to-node-stream)
[![BrowserStack Status](https://www.browserstack.com/automate/badge.svg?badge_key=SWR6dmZVZG1nQkFjM2xuVVBIMk9WcW9qWkE3dS9DZytJL1NJWkhLcERPTT0tLXZieHpCYmsrSHEwSVlZbmx0U1Zaa3c9PQ==--6060c5253c29686ef5db4d67dbe2fbd636932cb4)](https://www.browserstack.com/automate/public-build/SWR6dmZVZG1nQkFjM2xuVVBIMk9WcW9qWkE3dS9DZytJL1NJWkhLcERPTT0tLXZieHpCYmsrSHEwSVlZbmx0U1Zaa3c9PQ==--6060c5253c29686ef5db4d67dbe2fbd636932cb4)

# readable-web-stream-to-node

Converts a [Web-API readable stream](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader) into a [Node readable stream](https://nodejs.org/api/stream.html#stream_readable_streams).

## Installation
Install via [npm](http://npmjs.org/):

```bash
npm install readable-web-to-node-stream
```
or yarn
```bash
yarn add readable-web-to-node-stream
```

## Compatibility

Unit tests are performed on the following browsers:

*   Google Chrome 74.0
*   Firefox 68.0
*   Safari 12.0
*   Opera 60.0
 
## Examples

### Example written in JavaScript

Import readable-web-stream-to-node in JavaScript:
```JavaScript
const ReadableWeToNodeStream = require('readable-web-to-node-stream').ReadableWeToNodeStream;

async function download(url) {
    const response = await fetch(url);
    const readableWebStream = response.body;
    const nodeStream = new ReadableWeToNodeStream(readableWebStream);
}

```

### Example written in TypeScript

```TypeScript
import { ReadableWeToNodeStream } from 'readable-web-to-node-stream';

async function download(url) {
  const response = await fetch(url);
  const readableWebStream = response.body;
  const nodeStream = new ReadableWeToNodeStream(readableWebStream);
}
```

## API

**constructor(stream: ReadableStream): Promise<void>**

`stream: ReadableStream`: the [Web-API readable stream](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader).

**close(): Promise<void>**
Will cancel close the Readable-node stream, and will release Web-API-readable-stream.

**waitForReadToComplete(): Promise<void>**
If there is no unresolved read call to Web-API Readable​Stream immediately returns, otherwise it will wait until the read is resolved.

## Licence

(The MIT License)

Copyright (c) 2019 Borewit

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
