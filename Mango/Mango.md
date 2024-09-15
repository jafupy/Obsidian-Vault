# Mango

#Mango 

Mango is a performant, statically typed, compiled programming language with native XML / HTML support.

When you've finished reading through all the features, check out the [examples](https://github.com/TodePond/DreamBerd/blob/main/Examples.md).

## The Basics

You place your code in a `main` function, like this:

```

fn Main () {
	io.out("Hello World!"); // Hello World!
}
```

### Variables

There are 3 types of variables: constants, mutable variables & immutable variables. Types can be inferred, but it is recommended that you define them explicitly. When mutating a variable, the type must stay the same, unless your overriding a variable. 

#### Constants

Constants in Mango are immutable, and non-reassignable, and cannot be overwritten. Constants must be declared using SCREAMING/UPPER_SNAKE_CASE

```
const API_KEY: string = "abcd12345";

API_KEY = "not the original";       # ERROR #
API_KEY.push("h");                  # ERROR #
const API_KEY = "something else";   # ERROR #
```

#### Mutable Variables

Mutable variables in Mango are mutable, and reassignable, and can be overwritten

```
mut var foo = "bar";

foo.push(" bar");    # ALLOWED #
foo = "bar";         # ALLOWED #
mut var foo = 123;   # ALLOWED #
```

#### Immutable Variables

Immutable Variables are variables that are immutable, non-reassignable, but can be overwritten. They function like constants in JavaScript.

```
var commandments = [
"You shall have no other gods before Me.",
...
"You shall not covet",
];

commandments = [ ... ]                           #  ERROR  #
commandments.append("You shall not use Rust");   # ALLOWED #
var commandments = 123;                          # ALLOWED #
```

### Equality

Mango allows for two types of checks: loose and precise.

You can use `==` to do a loose check.

```
3.14 == "3.14"! //true
```

You can use `===` to do a more precise check.

```
3.14 === "3.14"! //false
```

### Datatypes

#### Arrays

Arrays start at `0`. Negative indexes go from the end of the Array

```
let scores: int[] = [1, 2, 3, 4, 5]

io.out(scores[0]) // 1
io.out(scores[-2]) // 4
```

#### Sets

Sets are a key/value store, accepting a string key and a value of any type. 

```
const person
```

## Time

Time is a built in class, 
## Events

In Mango, you can do stuff on event. Whether thats a built in event like a variable changing, or ones provided by a package. 

To listen to an event, you use the `on` decorator.  

```
let mut health = 100
@on health.events.update
fn onHealthUpdate () {
	if health == 0 {
		io.out("You died")
	}
}
```

## Decorators

Decorators are used to modify or extend the behaviour of functions without changing their actual code. 

```
@decorator( /*optional params*/ )
fn function () {
	...
}
```

## Loops

In Mango, there are two types of loops: `for` and `while`.

#### For Loops

For loops allow you too loop over arrays or keys.

```
for (i, index of var) {
	io.out(i, var, index)
}
```

## Installation

This language is not yet available.

## Formatting

In Mango, you choose how to format your code. Whitespace is insignificant. The Mango compiler has a built in opinionated formatter which is opt in.

## Functions

To declare a function, use the `fn` keyword. 

```
fn doSomething (params) {
	...
}
```

If you would like an anonymous function, you may use the syntax:

```

const myFunction = (params) -> {
	...
}

```

**Note:** Arrow functions in Mango work identically to arrow functions in JavaScript.

## Dividing by Zero

Dividing by zero returns `undefined`.

```
io.out(3 / 0)! //undefined
```

## Strings

Strings can be declared with single quotes or double quotes.

```
var name = 'Lu'!
var name = "Luke"!
```

### String Interpolation

For Interpolated strings, replace the quotes with \` character. You then surround your variable or expression in `${…}`

```
var fullName = `${lastName.toUpper()}, ${firstName}`
```

## Types

Type annotations are optional.

```java
var age: Int = 28!
```

By the way, strings are just arrays of characters.

```
String == Char[]!
```

Similarly, integers are just arrays of digits.

```
Int == Digit[]!
```

## Regular Expressions

You can use the regular expression type to narrow string values.

```
var email: RegExp<(...)> = "mymail@mail.com"!
```

## File Structure

By default, your source code lives in the `src/` directory inside your project folder. 

### Project Configuration File

Your project config 

### Import/Export

In Mango, you can split your code into multiple files, and then import everything into a single file using `module.imports` and `module.exports`.

```
module.imports {
	{ add, subtract, trigonometry.functions.sine } from "./utils"
	io from "io"
}

module.exports {
	trigonometry: {
		functions: {
		sine
		}
	}
}

```

## Classes

Classes are defined like this:

```
class Cat {
	readonly age;
	init() {
		...
	}
}
```

## Overloading

You can overload variables. The most recently defined variable gets used.

```java
const const name = "Luke"!
const const name = "Lu"!
print(name)! // "Lu"
```

Variables with more exclamation marks get prioritised.

```java
const const name = "Lu"!!
const const name = "Luke"!
print(name)! // "Lu"

const const name = "Lu or Luke (either is fine)"!!!!!!!!!
print(name)! // "Lu or Luke (either is fine)"
```

In the same spirit, you can use an inverted exclamation mark for negative priority.

```java
const const name = "Lu"!
const const name = "Luke"¡
print(name)! // "Lu"
```

## Semantic Naming

DreamBerd supports semantic naming.

```java
const const sName = "Lu"!
const const iAge = 29!
const const bHappy = true!
```

**New for 2023:** You can now make globals!

```java
const const g_fScore = 4.5!
```

## XML / HTML

You can embed XML / HTML in Mango. It's just Mango. And it's also just XML. HTML is written as XML.

```
fn page () {
	return <xml>
		<div> Hi </div>
		<h1 class="main"> Example </h1>
		</xml>
}
```

When inside XML, you are free to use any reserved keywords within XML. However, the xml tag is still reserved.

To use variables inside XML, use the following syntax: `{{% variableName %}}`. the `{{% %}}` syntax accepts any valid Mango expression. 

### Logic

If you wish to use if statements or loops in Mango XML, you can use the following special tags:

```
<#for ...>
	...
</for>

<while ...>

// -----------

<<if (...)>
	...
	<<else (Optional check. You can have multiple elses.)>>
		...
	<</else>>
<</if>>

```

**Note:** If you want a finel else statement without a condition, omit the ` ( ) `. 
**Note:** The `else` statements are entirely optional.
