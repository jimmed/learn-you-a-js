<!-- $theme: gaia -->

# Learn you a JS for great good!

### Lesson 1: *"How did it come to this?"*

---

# What is a JS?

 - Dynamic scripting language
 - Designed in 2 weeks in 1995
 - Still in use world-wide today

---

# The JS Ecosystem

 - V8
 - Node.js
 - npm
 - ECMAScript

---

# V8

 - JavaScript virtual machine
 - Heavily optimised
 - Used in node.js + Chrome
 - **Runs your code**
---

# Node.js

 - JavaScript runtime
 - Network + filesystem APIs
 - REPL
 - **Connects V8 to the outside world**

---

# npm

 - Package manager for node.js
 - Largest online repository of FOSS libraries
 - **Installs & manages libraries for node.js**

---

# ECMA

 - Not an acronym (!)
 - Standards body (like W3C)
 - Modernising and improving JS

---

# ECMAScript (ES)

 - **is another name for JavaScript**
 - defines incremental JS standards
   - ES2015, ES2016, ES2017 etc.

---

# Demo
## Using the Node.js REPL

---

# Demo
## Using the Node.js REPL

1. Launch node without any arguments

    ```bash
    $ node
    ```

2. Type a JS statement, get the result back

---

# Demo
## Using the Node.js REPL

```js
> 1 + 2
3

> 'hello there ' + process.env.USER + '!'
'hello there jim!'

> require('fs').readFileSync('./slides.md', 'utf8')
'# Learn you a JS for great good! [...]'
```

---

# Demo
## Running code from files

1. Launch node, passing your file path as an argument
    
    ```bash
    $ node demo1.js
    ```

2. Code will be executed... but no output?

---

# Demo
## Running code from files

```js
console.log(1 + 2)

console.log('hello there ' + process.env.USER + '!')

console.log(
  require('fs').readFileSync('./slides.md', 'utf8')
)
```

---

# Demo
## Running code from files

3. Use `console.log` to output something

	```bash
    $ node demo2.js
    ```
4. Re-run the code again, see the output!