captureweb [![NPM version](https://badge.fury.io/js/captureweb.png)](http://badge.fury.io/js/captureweb) [![Build Status](https://travis-ci.org/darul75/captureweb.png?branch=master)](https://travis-ci.org/darul75/captureweb) [![Total views](https://sourcegraph.com/api/repos/github.com/darul75/captureweb/counters/views.png)](https://sourcegraph.com/github.com/darul75/captureweb)
=====================

Capture websites with screenshot or pdf.

* By default a small node server handle request and conversion, default port 5001
* By default another small node server handle request as a proxy client, default port 5002

But you do not have to worry to much about it.

Demo
------------
http://darul-demo.herokuapp.com/captureweb

Installation
------------

Using npm:

```
npm install captureweb
```


Usage
-------------

```javascript
var captureweb = require('captureweb');

captureweb.capture({
      url: 'https://github.com', 
      mime: 'image/png', 
      viewportSize: { width: 1280, height: 1024 } 
      }, function(err, stream) {
  // process err
  
  // handle stream, by instance with server response
  res.writeHead(200, {'Content-Type' : mime});

  stream.pipe(res);
  
  // or with basic event 
  var data = '';		        

  stream.on('data', function(d){ 
    data += d; 
  });

  stream.on('end', function(){
		
  });
	
  // ...
	
});
```    
    
## Parameters

- **url** site to capture https://www.google.fr/#q=captureweb
- **mime** mime type 'image/png', 'application/pdf'
- **viewportSize** embedded json {width: 200, height: 222}
- MORE COMING SOON

### Build

You can run the tests by running

```
npm install
```
or
```
npm test
```

assuming you already have `grunt` installed, otherwise you also need to do:

```
npm install -g grunt-cli
```

## License

The MIT License (MIT)

Copyright (c) 2013 Julien Valéry

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.




