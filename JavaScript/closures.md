```JavaScript
function greet(whattosay) {

  return function(name) {
    console.log(`${whattosay} ${name}`);
  };

}

let sayHi = greet("Hi");
sayHi("Tyler");
greet("Hi")("Tyler");
```

closures are a feature of the JavaScript language.
We rely on this feature, alot.

# Classic Examle

```JavaScript
function buildFunctions() {
  var arr = [];

  for (var i = 0; i < 3; i++) {
    arr.push(function() {
      console.log(i);
    });
  }
  return arr;
}

var fs = buildFunctions();

fs[0]();
fs[1]();  
fs[2]();
```

output:

```Bash
$ node app.js
3
3
3
```
