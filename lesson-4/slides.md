<!-- $theme: gaia -->
<!-- $size: 16:9 -->

# Learn you a JS for great good!

#### Lesson 4: _"Functions, Prototypes and Classes"_

---

# Functions

 - Take one or more parameters
 - Return a single value

---

# Functions

```js
function sum (a, b) {
  return a + b
}

> sum(2, 3)
5
```

---

# Anonymous functions

```js
function (a, b) {
  return a + b
}
```

```js
const sum = function (a, b) {
  return a + b
}
```

---

# Arrow Functions

 - **Shorthand syntax** for functions
 - Introduced in ES2015
 - Subtle differences *(which we'll cover in a later lesson)*

---

# Arrow functions

```js
const sum = (a, b) => {
  return a + b
}
```
 - Regular old function block
 - `return` must be used explicitly

```js
const sum = (a, b) => a + b
```

 - Single expression
 - Implicit `return`

---

# Functions as constructors

```js
function Circle (radius) {
  this.radius = radius
}
```

 - What's different about this?

---

# Functions as constructors

```js
function Circle (radius) {
  this.radius = radius
}
```

 - Capital `S`
 - `this` keyword
 - No `return` statement

---

# Constructors

```js
function Circle (radius) {
  this.radius = radius
}

Circle.prototype.area = function () {
  return Math.PI * (this.radius ** 2)
}

Circle.prototype.circumference = function () {
  return 2 * Math.PI * this.radius
}
```

---

# Constructors

 - &hellip;are just functions
   - *(any function can be a constructor if invoked with `new`)*
 - &hellip;create new objects with additional properties and methods

---

# The `new` keyword

```js
> const myCircle = new Circle(3)

> myCircle
Circle { radius: 3 }

> myCircle.radius
3
```

---

# The `new` keyword

```js
> myCircle.area()
28.274333882308138

> myCircle.circumference()
18.84955592153876
```

---

# Prototypes

 - In JavaScript, *everything* is an object, even numbers!
 - All objects have a `prototype` property
 - The prototype defines defaults for all new instances of it
 - New types can be made by *inheriting* other prototypes

---

# WAT?

---

# Prototypes

```js
function User (name, permissions) {
  this.name = name
  this.permissions = permissions
}

User.prototype.greet = function () {
  return "Hey there, " + this.name
}

User.prototype.hasPermission = function (permission) {
  return this.permissions.includes(permission)
}
```

---

# Prototypal *inheritance*

```js
function AdminUser (name) {
  this.name = name
}

Object.assign(AdminUser.prototype, User.prototype)

AdminUser.prototype.hasPermission = function () {
  return true
}
```

---

# This smells an awful lot like class-based OOP to me, Jim

### &hellip;and you said it wasn't&hellip;

###### <small>&hellip;and that looked a lot like a class being extended&hellip;</small>

---

# Classes

 - Added in ES2015
 - **Shorthand syntax** for prototypal inheritance pattern
 - Looks a *lot* like class-based OOP, but **it is not**

---

# Classes

```js
class Circle {
  constructor(radius) {
    this.radius = radius
  }
  
  area() {
    return Math.PI * (this.radius ** 2)
  }
  
  circumference() {
    return 2 * Math.PI * this.radius
  }
}
```

---

# Classes

```js
class User {
  constructor(name, permissions) {
    this.name = name
    this.permissions = permissions
  }
  
  greet() {
    return "Hey there, " + this.name
  }
  
  hasPermission(permission) {
    return this.permissions.includes(permission)
  }
}
```

---

# Classes

```js
class AdminUser extends User {
  hasPermission() {
    return true
  }
}
```

---

# If you've ever seen any React code&hellip;

```js
class MyAwesomeButton extends React.Component {
  render() {
    return (
      <button disabled={this.props.disabled}>{this.props.children}</button>
    )
  }
}
```

---

# Review

 - Everything is an object
 - Every object has a prototype
 - The prototype defines defaults for all new instances of an object
 - New types can be made by *inheriting* other prototypes
