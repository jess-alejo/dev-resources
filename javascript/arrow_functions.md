### ES6 Refresher

##### Arrow functions

Sometimes called _fat_ arrow functions or _lambda functions_, it is most often used to shorted function declarations

```javascript
// a function that checks if a number is an odd number
const isEvenNumber = function (number) {
  return number % 2 === 0
}
```

```javascript
// using arrow function, we ommit the function keyword, and
// we prepend the block with a =>
const isEvenNumber = (number) => {
  return number % 2 === 0
}

// if we have only one argument, we can remove the
// parenthesis around it
const isEvenNumber = number => {
  return number % 2 === 0
}

// if the code block has only one line, we can remove the
// curly braces
const isEvenNumber = number => return number % 2 === 0

// and tidy it up further by removing the return keyword
const isEvenNumber = number => number % 2 === 0
```

- arrow functions don't rebind the `this` keyword

##### Array.map

Used to transform an element of an array.

```javascript
const fruits = ["apple", "banana", "cherry"]
const items = fruits.map(fruit => `<li>${fruit}</li>`)
```

`${}` - argument placeholder

##### Object Destructuring

Used to simplify the assigning object properties into a variable.

```javascript
// given a person object

const person = {
  lastName: "Doe",
  firstName: "John",
  middleName: "Smith",
  suffix: "III",
}
```

```javascript
// before, we initialize and assign the variables like this

const lastName = person.lastName
const givenName = person.firstName
const middleName = person.middleName
```

```javascript
// using object destructuring

const { lastName, firstName: givenName, middleName } = person
```

##### Spread Operator

Used to expand an iterable (array, string, object)

```javascript
// combine an array
const first = [1, 2, 3]
const second = [4, 5, 6]

// before
const combined = first.concat(second)

// using spread operator `...`
const merged = [...first, ...second]
```

```javascript
// we can also insert an item anywhere
const combined = [...first, "a", ...second, "b"]
```

```javascript
// we can convert a string into an array of characters
const string = "The quick brown fox jumps..."
const chars = [...string]
```

```javascript
// we can also combine objects
const person = { firstName: "John", lastName: "Doe" }
const address = { address: "", city: "", state: "" }

const profile = { ...person, ...address }
```
