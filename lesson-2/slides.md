<!-- $theme: gaia -->
<!-- $size: 16:9 -->


# Learn you a JS for great good!

#### Lesson 2: _"A little knowledge is a dangerous thing"_

---

# Basic Types & Operators

* Booleans
* Numbers
* Strings
* (`null` and `undefined`)

---

# Basic Types

## Booleans

* Can be either `true` or `false`

---

# Basic Types

## Booleans

* "Not" operator: `!`
* For example:

  ```js
  > !true
  false

  > !false
  true

  > !!true
  true
  ```

---

# Basic Types

## Booleans

* "And" operator: `&&`

  ```js
  > true && true
  true

  > true && false
  false
  ```

* "Or" operator: `||`

  ```js
  > true || false
  true

  > false || false
  false
  ```

  ---

  # Basic Types

  ## Booleans

  * "And" operator: `&&`

    ```js
    > 3 && 4
    4

    > 12 && 0 && 2
    0
    ```

  * "Or" operator: `||`

    ```js
    > 1 || 0
    1

    > 2 || 3
    2
    ```

---

# Basic Types

## Booleans

* Strict equality: `===`
* Strict inequality: `!==`

* For example:

  ```js
  > true === true
  true

  > true === false
  false

  > true !== true
  false

  > true !== false
  true
  ```

---

# Basic Types

## Numbers

* Single type for all numbers (integer or floating point)
* Accurate _enough_ for the web

---

# Basic Types

## Numbers / Maths

* Addition: `+`
* Subtraction: `-`
* Division: `/`
* Multiplication: `*`

---

# Basic Types

## Numbers / Maths

```js
> 2 * 3
6

> (5 + 2) * 3
21
```

---

# Basic Types

## Numbers / Maths

* Modulo (a.k.a. "remainder"): `%`
* For example:

  ```js
  > 6 % 3
  0

  > 7 % 3
  1

  > 8 % 3
  2

  > 9 % 3
  3
  ```

---

# Basic Types

## Numbers / Comparison

* Greater than: `>`
* Greater than or equal: `>=`
* Less than: `<`
* Less than or equal: `<=`

---

# Basic Types

## Numbers / Comparison

* Strict equality: `===`
* Strict inequality: `!==`
* For example:

  ```js
  > 1 === 1
  true

  > 1 === 2
  false
  ```

---

# Basic Types

## Strict vs. loose equality

* Loose quality: `==`
* Loose inequality: `!=`

```js
> 1 == true
true

> 1 === true
false

> 0 == false
true

> 0 == true
false
```

* Positive numbers are *truthy*
* Negative numbers (and `0`) are *falsey*

---

# Basic Types

## Strict vs. loose equality

* Strict equality (`===`): both values are the **same type** and are equal
* Loose equality (`==`): both values are equal **when coerced to the same type**

---

# Basic Types

## Strings

* Essentially just text
* For example:

  ```js
  > "hello world"
  'hello world'
  ```

---

# Basic Types

## Strings

* Concatentation: `+`
* For example:

  ```js
  > 'hello there ' + 'my friend'
  'hello there my friend'
  ```

---

# Basic Types

## Strings

* Strings have a length property

  ```js
  > 'Jim O\'Brien'.length
  11
  ```

* Can address each character numerically

  ````js
  > 'Jim O\'Brien'[6]
  'B'
  		```
  ````

---

# Basic Types

## Coercing Strings

```js
> 'I am ' + 29 + ' years young'
'I am 29 years young'
```

```js
> 29 == "29"
true
```

```js
> 29 === "29"
false
```

---

# Basic Types

## Coercing Strings

```js
> 'hello' == true
true

> '' == true
false

> '' === false
false
```

Strings are truthy if their length is greater than 0

---

# Compound Types

## Arrays

* List of items

  ```js
  [1, 2, 3, 4, 5]
  ```

  ```js
  ['Rizwan', 'Nikki', 'Abhi', 'Xhoi']
  ```

---

# Compound Types

## Arrays

* Can contain any type
* Can be nested

  ```js
  [1, 'Rizwan', 455, true, [3, 5, 7]]
  ```

---

# Compound Types

## Arrays

* Have a length property

  ```js
  > [ 1, 4, 9, 16, 25 ].length
  5
  ```

* Can address each item numerically

  ```js
  > [ 1, 4, 9, 16, 25 ][2]
  9
  ```

* _Strings are essentially arrays of characters!_

---

# Compound Types

## Arrays / Comparison

* Cannot use equality operators on arrays in the way you'd think:

  ```js
  > [1, 2, 3] === [1, 2, 3]
  false

  > [1, 2, 3] == [1, 2, 3]
  false
  ```

* Why do you suppose this is?

---

# Compound Types

## Objects

* Key/value pair
* Keys are strings
* Values can be any type

---

# Compound Types

## Objects

```js
{
  name: 'Jim',
  age: 29,
  friends: ['Rizwan', 'Xhoi', 'Abhi', 'Nikki']
}
```

* Remarkably similar to JSON, a.k.a. **JavaScript Object Notation**

---

# Compound Types

## Objects

* Access values using 'dot' notation:

  ```js
  > user.name
  'Jim'

  > user.age
  29

  > user.friends[1]
  'Xhoi'
  ```

* or using square bracket notation (just like an array):

  ```js
  > user['name']
  'Jim'
  ```

---

# Compound Types

## Objects

* Use `Object.keys(obj)` to get an array of all keys:

  ```js
  > Object.keys(user)
  [ 'name', 'age', 'friends' ]
  ```

* Use `Object.values(obj)` to get an array of all values:

	```js
  > Object.values(user)
  > [ 'Jim', 29, ['Rizwan', 'Xhoi', 'Abhi', 'Nikki'] ]

  ```

---

# Compound Types

## Objects

* Use `Object.entries(obj)` to get an array of all key/value pairs:

  ```js
  > Object.entries(user)
  [
    ['name', 'Jim'],
    ['age', 29],
    ['friends', ['Rizwan', 'Xhoi', 'Abhi', 'Nikki']]
  ]
  ```

---

# `null` and `undefined`

* `undefined` is the **absence** of a value
* `null` is the **presence** of no value

---

# `null` and `undefined`

* WAT?

---

# `null` and `undefined`

```js
> const someObject =
  {
    a: 'foo',
    b: 'bar',
    c: null
  }

> someObject.a
'foo'

> someObject.c
null

> someObject.z
undefined
```
