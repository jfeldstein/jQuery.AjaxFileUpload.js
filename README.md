This plugin uploads the file somehwere, and passes the
response to a callback, nothing else. 

- It does not depend on specific HTML, just give it a `<input type="file">`
- It does not require your server to respond in any particular way
- It does not matter how many files you use, or where they are on the page

**Simple HTML**

    <input type="file" id="one-specific-file" name="one-specific-file">

**Use as little as**

    $('#one-specific-file').ajaxfileupload({
      action: '/upload.php'
    });

**or as much as**

    $('input[type="file"]').ajaxfileupload({
      action: '/upload.php',
      valid_extensions : ['md','csv'],
      params: {
        extra: 'info'
      },
      onComplete: function(response) {
        console.log('custom handler for file:');
        alert(JSON.stringify(response));
      },
      onStart: function() {
        if(weWantedTo) return false; // cancels upload
      },
      onCancel: function() {
        console.log('no file selected');
      }
    });


Copyright (c) 2011 Jordan Feldstein

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
