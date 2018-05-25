<!-- $theme: gaia -->

# Learn you a JS for great good!

Lesson 3: *"Expressions, statements and variables"*

---

# Expressions

 - Anything that **evaluates to a value**
 - Can be used anywhere that expects a value

---

# Expressions

```js
> 3
3

> 3 * 3 + ' bottles of beer'
'9 bottles of beer'

> require('fs').readFileSync('./slides.md', 'utf8')
'# Learn you a JS for great good! [...]'
```

---

# Variables

 - Re-usable references to values
 - Originally used the `var` keyword
 - Modern ECMAScript uses `const` or `let` keywords

---

# Assigning Variables

 - Assign the result of an expression to a variable:

    ```js
    > const colour = 'blue'
    
    > const age = 29
    
    > const something = age + colour
    
    > something
    '29blue'
    ```
 
---

# Reassigning Variables

 - Variables declared with `const` may never be reassigned or re-declared

    ```js
    > const x = 1
     
    > x = 2
    TypeError: Assignment to constant variable.

    > const x = 3
    SyntaxError: Identifier 'x' has already been declared
    ```

---

# Reassigning Variables

 - Variables declared with `let` may be reassigned, but not re-declared:

    ```js
    > let x = 1
    
    > x = 2
    2
    
    > let x = 3
    SyntaxError: Identifier 'x' has already been declared
    ```

---

# Reassigning Variables

 - Variables declared with `var` may be reassigned or re-declared *without error*:

    ```js
    > var x = 1
    
    > x = 2
    2
    
    > var x = 3
    
    > x
    3
    ```
    
 - This is why we **don't use `var` any more**!