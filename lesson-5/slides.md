<!-- $theme: gaia -->
<!-- $size: 16:9 -->

# Learn you a JS for great good!

#### Lesson 5: _"Can we please learn something useful now?"_

---

# Control statements

 - Conditionals
 - Loops

---

# Conditional statements

### `if`/`else`

```js
if (dog.isGoodBoy) {
  dog.giveTreat()
} else {
  human.explainTo(dog, 'No.')
}
```

---

# Conditional statements

### `if`/`else`

```js
const shouldGiveTreat = (dog) => {
  if (dog.isGoodBoy) {
    return true
  } else {
    return false
  }
}
```

---

# Conditional statements

### Ternary operator

```js
const shouldGiveTreat = (dog) => dog.isGoodBoy ? true : false
```

---

```js
const shouldGiveTreat = (dog) => dog.isGoodBoy
```

---

# `switch` statement

```js
// To stop doggo getting too hefty
const getMaximumDogTreatsPerDay = (dog) => {
  switch (dog.breed) {
    case 'Husky':
      return 20
    case 'Labrador':
    case 'Shiba Inu':
    case 'Golden Retriever':
      return 3
    case 'Dachshund':
      return 2
    default:
      return 1
}
```

---

# `switch` statement

 - Finds the first `case` whose value loosely equals (`==`) the `switch` value
 - Executes any further statements until `return` (or `break`)
 - Hangover from C that is generally best avoided

---

# Loops

### `while` loops

```js
const maximumTreats = getMaximumDogTreatsPerDay(dog)

while (dog.treatsEatenToday <= maximumTreats) {
  dog.giveTreat()
}
```

 - Most basic loop
 - Executes the statement block repeatedly until condition is falsey
 - Easy to create infinite loops!

---

# Loops

### `for` loops

```js
for (let i = 0; i < 10; i++) {
  console.log(i)
}
```

 - Second-most basic loop
 - Incredibly hard to summarize
 - Avoid using if alternatives are available

---

### `for` loops

```js
const names = ['Xhoi', 'Abhi', 'Nikki', 'Rizwan']

for (let i = 0; i < i.length; i++) {
  console.log("Hey there, " + names[i])
}
```

 - Ideal for iterating over loops
 - But there are much _cleaner_ ways

---

### ~~loops~~

## Array functions

---

# Finally something useful

```js
const names = ['Xhoi', 'Abhi', 'Nikki', 'Rizwan']

> names.forEach(name => console.log(name))

> names.map(name => `Hey there, ${name}!`)

> names.filter(name => name.length < 5)

> names.some(name => name.contains('j'))

> names.every(name => name.contains('i'))
```

---

# A note on closures

```js
function makeGreeter(name) {
  const greeting = `Hey there, ${name}`
  
  return function greeter() {
    console.log(greeting)
  }
}
```

---
# A note on closures

```js
const makeGreeter = name => {
  const greeting = `Hey there, ${name}`
  
  return () => console.log(greeting)
}
```

---

# `reduce`

```js
const numbers = [1, 2, 3, 4]

const total = numbers.reduce((totalSoFar, number) => totalSoFar + number, 0)
```

---

# `reduce`

```js
const names = ['Xhoi', 'Abhi', 'Nikki', 'Rizwan']

const nameLengths = names.reduce((lengths, name) => {
  lengths[name] = name.length
  return lengths
}, {})
```

---

# *[insert awkward segue here]*

---

# Destructuring assignment

```js
const numbers = [1, 2, 3, 4, 5]

const [first, second, ...rest] = 

> first
1

> second
2

> rest
[3, 4, 5]

> [first, second, ...rest]
```

---

# Destructuring assignment

```js
const { age, name, ...rest } = getUserByName('jim')

> age
29

> name
'Jim'

> rest
{ dateOfBirth: new Date(1989, 1, 26) }
```

---

# HOMEWORK!

---

# Homework Assignment

```js
function map(array, fn) {}
```

**Goal:** Implement `map` so that it behaves exactly like `array.map(fn)`.

 - It should return the result of applying `fn` to each element of `array`, as a new array.

**Rules:**

 1. You may not use any of the loops taught in this lesson.
    - No `for`, `while`, `forEach`, `map` or `reduce`.
