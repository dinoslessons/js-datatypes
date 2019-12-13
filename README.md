# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  WEB DEVELOPMENT IMMERSIVE

# JavaScript Data Types Lesson


# Objectives
*After this lesson, students will be able to:*
- Understand JavaScript Data Types

# JS Data Types

The latest ECMAScript standard defines seven data types:
- Number
- String
- Boolean
- Null
- Undefined
- Symbol
- Object
- Arrays (kinda)

# Number Data Type
JavaScript supports both integer and floating-point numbers that can be represented in decimal notation. Unlike other languages, JavaScript does not treat integer and floating-point numbers differently. All numbers in JavaScript are represented as floating-point numbers. 

Here's an example demonstrating the numbers in different formats:
```js
var x = 2;  // integer number
var y = 3.14;  // floating-point number
```

>Note: Technically speaking, JavaScript estimates numbers. It just does it to such a depth of precision that it's normally impossible to notice, but it's worth knowing as it can cause errors in a small number of cases. Perhaps the most common case is `0.1 + 0.2`. Give it a shot and check the answer. You might be surprised!

## Arithmetic Operators
The standard [arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Arithmetic_operators) that you've been learning since grade school are supported in JavaScript, including addition, subtraction, multiplication, division, and modulus (aka getting the  "remainder").  

Check it out:

```javascript
// addition
1 + 2
=> 3

// subtraction
2 - 5
=> -3

// division
5 / 2
=> 2.5

// multiplication
6 * 2
=> 12

// modulus (getting the remainder from division)
3%2
=> 1
```

>Note: modulus is often used to separate even and odd numbers, as the remainder of **all** even numbers when divided by 2 is 0. `if(num%2 === 0){ // num is even}`

#### Special Number Operators

For advanced math in JavaScript, there is a special `Math` object with some very useful methods.

- Need to figure out some exponents? Then just use `Math.pow(number, power)`. 
 >Note: People often refer to exponents as "taking a number to the x power". Think of that when you need to remember `Math.pow`.

```javascript
// 3^2 becomes
Math.pow(3,2)
=> 9

// 2^4 becomes
Math.pow(2,4)
=> 16
```
- Need to figure out the square root of a number? Use `Math.sqrt(number)`

```javascript
// √4 becomes
Math.sqrt(4)
=> 2
```
- Need a `random` number? Then use `Math.random()`.

```javascript
// The following only returns a random decimal between 0 and 1.
Math.random()
=> .229375290430

// The following will return a random number between 0 and 10
Math.random()*10
=> 9.430395229784267
```
- Need a random integer? Well, let's first discuss rounding decimals to the nearest integer. Since Numbers can be **Floats** or **Integers** we often want to get rid of remaining decimal places, which can be done using `Math.floor`, `Math.ceil`, or `Math.round`.

```javascript
// round DOWN to the nearest integer
Math.floor(3.14)
=> 3
Math.floor(3.9999)
=> 3

// round UP to the nearest integer
Math.ceil(3.14)
=> 4
Math.ceil(3.9999)
=> 4

// Mathematically round to the nearest integer
Math.round(3.14)
=> 3
Math.round(3.9999)
=> 4
```

— Need a random integer between two specific integers? Combine `.random()` and `.floor()`.
```
// random integer between 1 and 10
Math.floor(Math.random() * 10) + 1 

// random integer between num1 and num2
Math.floor(Math.random() * num2) + num1
```

# String Data Type

Strings are collections of letters and symbols known as *characters*, and we use them to deal with words and text in JavaScript. Strings are just another type of **value** in Javascript.

There are **three** ways to write a string in JavaScript.
1. Surround a word or phrase with double quotes, 
```
"like this"
```
2. Surround a word or phrase with single quotes, 
```
'like this'
```
3. Surround a word or phrase with backticks (below the tilde key), 
```
`like this`
```

#### String Interpolation
When you wrap a string with backticks, you can insert JavaScript variables and expressions into that string. This is called **"string interpolation."** The syntax looks like this:

```
const firstName = "Brian"
const age = 33

`My name is ${firstName} and on my next birthday, I will be ${age + 1} years old.`
```

As you can see, string interpolation provides an easy way to inject variables or do basic math or logic functions dynamically. **You will likely use string interpolation A LOT.**


#### String helper methods
Methods are JavaScript functions that are built into the language can be attached to a piece of data with the following syntax: `.method`

For example, to find the number of letters in a string (aka the string's length), access its [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length) property:

```js
'hello'.length;
=> 5
```

Strings have other [methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Methods) as well that allow you to manipulate the string and access information about the string:

```js
// to grab a particular character:
'hello'.charAt(0);
=> "h"

// to replace one string with a new one:
'hello, world'.replace('hello', 'goodbye');
=> "goodbye, world"

// to make a string uppercase
'hello'.toUpperCase();
=> "HELLO"
```

Types of values like `Number` or `String` are not very useful without being able to form **Expressions** or **Combinations**.

Try your favorite number operators as expressions:

```javascript
  1 + 1
  => 2
  2 - 1
  => 1
```

You can also create expressions with strings using the addition operator:

```javascript
  'Hello, ' + 'world!'
  => "Hello, world!"
```

This is called **String Concatentation.**

> Note: the 'plus' binary operator is said to be "**overloaded**"— meaning that it behaves differently depending on what's on either side of it.
> Consider the following expressions. What do they output, and why?
> `1 + 2 + '3'` vs `'1' + 2 + 3`



#### Converting Strings to Integers with parseInt() and parseFloat()

You can convert a string to an integer using the built-in [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) function.

```javascript
parseInt('123');
=> 123

parseInt('010');
=> 10
```

This will be important later when we're taking user input from the web and using it on our server or in our browser to do some type of numeric calculation.


Similarly, you can parse floating point numbers using the built-in [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) function.

```javascript
parseFloat('11.2');
=> 11.2
```

You can also use the unary `+` operator to convert values to numbers:

```javascript
+"42";
=> 42
```

#### NaN

The `parseInt()` and `parseFloat()` functions parse a string until they reach a character that isn't valid for the specified number format, then return the number parsed up to that point. However the "+" operator simply converts the string to `NaN` if there is any invalid character in it.


A special value called [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) (short for "Not a Number") is returned if the string is non-numeric:

```javascript
parseInt('hello');
=> NaN
```

**`NaN` is toxic**: if you provide it as an input to any mathematical operation the result will also be `NaN`:

```javascript
NaN + 5;
=> NaN
```

You can test for `NaN` using the built-in [`isNaN()`](ttps://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN) function:

```js
isNaN(NaN);
=> true
```
JavaScript's numeric operators are `+`, `-`, `*`, `/` and `%` and all work as you expect and should have practiced during your pre-work.

# Boolean Data Type

Boolean represents a logical entity and can have two values: `true`, and `false`.

<img src = "Truth_table_for_AND,_OR,_and_NOT.png">


#### Truthy & Falsey

#### All of the following become false when converted to a Boolean

- `false`
- `0`
- `''` (empty string)
- `NaN`
- `null`
- `undefined`

#### All other values become true when converted to a Boolean

There is a simple way of verifying the truthiness or falsiness of a value. When you add `!` in front of a value, the returned value will be the inverse of the value in a boolean. So if you add two `!` then you'll get the boolean value of the original one:

```javascript
!!1
//=> true

!!0
//=> false

!!-1
//=> true

!![]
//=> true

!!{}
//=> true

!!null
//=> false

!!""
//=> false
```

#### Boolean/Logical Operators

[Logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

Logical operators will always return a boolean value `true` or `false`.

There are two "binary" operators that require two values:

- **AND**, denoted `&&`
- **OR**, denoted `||`

A third "unary" operator requires only one value:

* **NOT**, denoted `!`

#### && (AND)

The `&&` operator requires both left and right values to be `true` in order to return `true`:

```javascript
true && true
//=> true
```

Any other combination is false.

```javascript
true && false
//=> false

false && false
//=> false
```

#### || (OR)

The `||` operator requires just one of the left or right values to be `true` in order to return true.

```javascript
true || false
//=> true

false || true
//=> true

false || false
//=> false
```

Only `false || false` will return `false`

The `!` takes a value and returns the opposite boolean value, i.e.

```javascript
!true
//=> false
```

# Null Data Type

The value null represents the intentional absence of a value.

```javascript
let trigger = null;
```

# Undefined Data Type

A variable that has not been assigned a value has the value undefined.

```javascript
let count;
```

# Symbols Data Type

A Symbol is a unique and immutable primitive value and may be used as the key of an Object property. See next section for example.

# Objects Data Type

Objects are a collection of properties. We will cover objects in-depth in a later lesson; however, let's see an example:

```
const brian = {
  firstName: "Brian",
  lastName: "Flynn",
  nickName: "Brian Danger Flynn",
  pronouns: "He / Him",
  luckyNumber: 21,
  favoriteMovies: ["Almost Famous", "Big Fish", "Princess Mononoke"],
  favoriteRestaurants: [{
      type: "fast food",
      name: "Popeye's Lousiana-Style Fried Chicken",
      likes: ["3 piece chicken", "mashed potatoes", "biscuit"]
    }, {
      type: "ramen",
      name: "Jinn Ramen",
      likes: ["tonkatsu ramen", "spicy tonkatsu ramen"]
    }, {
      type: "buffet",
      name: "Essen",
      likes: ["pork belly", "shrimp gazpacho", "mashed potatoes"]
    }],
  hasPets: true
};
```

## Mini Lab: Objectify Your Neighbor
Using the example above, interview your neighbor and collect their first name, last name, nick name (if they don't have one, right `null`, pronouns, lucky number, favorite movies, favorite restaurants, and whether or not they have pets.

Write their answers down as an object —— **paying close attention to proper syntax** —— and Slack it out to the class.


