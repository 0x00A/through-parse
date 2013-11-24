# SYNOPSIS
Breaks out `parse()` from event stream, emits errors instead of `console.error()`.

# USAGE
```js
var parse = require('through-parse')

stream
  .pipe(parse())
  .pipe(through(function(obj) {
  	if (obj.id == 'foo') {
  	  obj.id = 'bar'
  	  this.push(obj)
  	}
  }).pipe(stream)
```
