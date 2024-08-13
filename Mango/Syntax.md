Mango is a hypothetical general purpose programming language. This language is a hybrid interpreted/compiled language, where during dev it would be run by an interpreter, and then when you're building for production, you would compile the language into a binary executable. The language is interpreted, but you have optional type definitions.

## Files
**File Extension:** `.mg`
The Language uses standard plain-text files with the extension `.mg`. 

## Variables
In Mango, there are three variable types:
### Constant
These variables are immutable, non-reassignable and once its set then they cannot be changed in any way, shape or form.
```ts
const APIKey: string = "0ai23ncs"
```

## Mutable variable
Mutable variables are you standard variables that you can manipulate and reassign
```ts
let mut shoppingList = [
	"Bread", 
	"Milk",
	"Cookies",
	"Mangos"
]

shoppingList.remove(1) // Allowed
shoppingList = [ /* Some new Array */ ] // Allowed
```

### Immutable variable
Immutable variables cannot be reassigned, but can be manipulated, eg. using `[list].remove(1)` syntax.
```ts
let users= [
	{
		id: "xbcd-1943-vngf-djrf",
		name: "John",
		email: "john@example.com",
	},
	{ /* ... */},
	// ...
]

users.append([{...}]) // Allowed
users = [...] // Not Allowed
```

## Datatypes

### String
Variable width text. If you would like to set a length, either min, max or both you can use type props.
```
let someString: String = "My Name is John" // String, any length
let 2chString: String(2) = "ab" // String, 2char length. throws error if string length is either too small or too big.
```
### Integer
Any whole number. By default i32, but can be changed at initialisation to any integer size, if needed, using a type prop.
```

```