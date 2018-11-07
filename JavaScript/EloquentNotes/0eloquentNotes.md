# Eloquent JavaScript Notes

## Introduction

"It is up to you to make the necessary effort. When you are struggling to follow the book, do not jump to any conclusions about your own capabilities. You are fine—you just need to keep at it. Take a break, reread some material, and make sure you read and understand the example programs and exercises. Learning is hard work, but everything you learn is yours and will make subsequent learning easier.

'When action grows unprofitable, gather information; when information grows unprofitable, sleep.'

Ursula K. Le Guin, The Left Hand of Darkness
"

"A program is a building of thought. It is costless to build, it is weightless, and it grows easily under our typing hands. But without care, a program’s size and complexity will grow out of control, confusing even the person who created it. Keeping programs under control is the main problem of programming. "

"There are many terrible mistakes to make in program design, and you should go ahead and make them so that you understand them. "

### Why Language Matters

```JavaScript
let total = 0, count = 1;
while (count <= 10) {
  total += count;
  count += 1;
}
console.log(total);
// → 55
```

BTW, same operation in Python:

```Python
sum(range(1,11))
## → 55
```

### What is JavaScript?

- introduced in 1995
- ECMAScript === JavaScript
- JavaScript is ridiculously liberal in what it allows.
- MongoDB and CouchDB, use JavaScript as their scripting and query language.

### Code, and What to do with it

- Code: the text that make up programs
- reading code and writing code are indispensable parts of learning to program.

### Book Overview

- three parts:
  1.  first 12 chapters are the JavaScript Language
  2.  next 7 are about JavaScript and the web
  3.  2 chapters on Node.js

```JavaScript
function factorial(n) {
  if (n === 0) {
    return 1;
  } else {
    return factorial(n - 1) * n;
  }
}
```
