Async programming with Node.js. At first, I was skeptical, I tried Node a bunch of times in the past but to no avail. I didn't understang any of it, much less any frameworks like express. About a year later, I tried [Nodeschool](http://nodeschool.io/) and out of nowhere, eveything clicked. It made sense, and I kind of liked it. Today I learned how Node works with async programming and the arguments that are passed through the command line, as well as the ```fs``` library.

```javascript
var fs = require('fs')
var path = process.argv[2]
var files

function fileLog(files) {
  console.log(files)
}

function readDirectory(callback) {
  fs.readFile(path, function(error, data){
    files = data.toString().split('\n')
    callback(files)
  })
}


readDirectory(fileLog)
```

Basically, the ```readDirectory``` function will call the ```readFile``` function to do it's work and then continue with the script. since there isn't anything else to do, after the ```readFile``` function is done it will call it's callback function, which is ```fileLog``` in this case. This is useful when you don't want *block* your program while it calls and API (for example). With callbacks and async programming, you program calls the API and then does something else, and when it's done, it fires the callback function. :D