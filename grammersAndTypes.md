# JavaScript Grammar and types

## **Basics**

JavaScript is case-sensitive and uses the Unicode character set. For example, the word Früh (which means "early" in German) could be used as a variable name.

```javascript
const Früh = "foobar";
```

But, the variable **früh** is not the same as **Früh** because JavaScript is case sensitive.

A **semicolon ( ; ) is not necessary** after a statement if it is written on its own line. **But if more than one statement on a line is desired, then they must be separated by semicolons**.

example -

```javascript
const someFunction = () => {console.log("Hello"); return "Hello"} // case semi colon needed

const a = 6; // ; not necessary 
const b = 9 

for() {
  console.log("hello 0) // ; not necessary
  console.log("hello 1) // ; not necessary
  console.log("hello 2) // ; not necessary

}
```

It is considered best practice, however, to always write a semicolon after a statement, even when it is not strictly needed. This practice reduces the chances of bugs getting into the code.

**The source text of JavaScript script gets scanned from left to right**, and is converted into a sequence of input elements which are tokens, control characters, line terminators, comments, or whitespace. (Spaces, tabs, and newline characters are considered whitespace.)

## **Comments in JS**

The syntax of comments is the same as in C++ and in many other languages:

```javascript
// a one line comment

/* this is a longer,
 * multi-line comment
 */
```

***You can't nest block comments. This often happens when you accidentally include a */ sequence in your comment, which will terminate the comment***

```javascript
/* You can't, however, /* nest comments */ SyntaxError */
```

In this case, you need to break up the */ pattern. For example, by inserting a backslash:

```javascript
/* You can /* nest comments *\/ by escaping slashes */
```

**Comments behave like whitespace, and are discarded during script execution.**

**Note: You might also see a third type of comment syntax at the start of some JavaScript files, which looks something like this: #!/usr/bin/env node.
This is called hashbang comment syntax, and is a special comment used to specify the path to a particular JavaScript engine that should execute the script**.

## **Declarations**

JavaScript has three kinds of variable declarations.

**var**  
Declares a variable, optionally initializing it to a value.

**let**  
Declares a block-scoped, local variable, optionally initializing it to a value.

**const**  
Declares a block-scoped, read-only named constant.

### Variables

You use variables as symbolic names for values in your application. The names of variables, called identifiers, conform to certain rules.

A JavaScript identifier usually starts with a letter, underscore (_), or dollar sign ($). Subsequent characters can also be digits (0 – 9). Because JavaScript is case sensitive, letters include the characters A through Z (uppercase) as well as a through z (lowercase).

```javascript
Some examples of legal names are Number_hits, temp99, $credit, and _name.

```

### Declaring variables

You can declare a variable in two ways:

With the keyword var. For example,

```javascript
var x = 42
```

This syntax can be used to **declare both local and global variables**, depending on the execution context.

With the keyword const or let. For example,

```javascript
let y = 13
```

This syntax can be used to declare a block-scope local variable. (See Variable scope below.)

You can declare variables to unpack values using the **destructuring assignment syntax**. For example,

```javascript
const { bar } = foo
```

This will **create a variable named bar** and assign to it the value corresponding to **the key of the same name from our object foo.**

Variables should always be declared before they are used. **JavaScript used to allow assigning to undeclared variables, which creates an undeclared global variable. This is an error in strict mode and should be avoided altogether**.

### Declaration and initialization

In a statement like

```javascript
let x = 42
```

, the **let x** part is called a declaration, and the

```javascript
= 42
```

part is called an initializer.

The declaration allows the variable to be accessed later in code without throwing a ReferenceError, while the initializer assigns a value to the variable. In var and let declarations, the initializer is optional. If a variable is declared without an initializer, it is assigned the value undefined.

In essence,

```javascript
let x = 42

// is equivalent to 

let x; x = 42.
```

**const declarations** always need an initializer, because they forbid any kind of assignment after declaration, and implicitly initializing it with undefined is likely a programmer mistake.

```javascript
const x; // SyntaxError: Missing initializer in const declaration
```

### Variable scope (Important)

A variable may belong to one of the following scopes:

- Global scope: The default scope for all code running in script mode.
- Module scope: The scope for code running in module mode.
- Function scope: The scope created with a function.

In addition, variables declared with **let** or **const** can belong to an additional scope:

Block scope: The scope created with a pair of curly braces (a block).

- When you declare a variable outside of any function, it is called a global variable, because it is available to any other code in the current document.
- When you declare a variable within a function, it is called a local variable, because it is available only within that function.

**let** and **const** declarations can also be scoped to the block statement that they are declared in.

```javascript
if (Math.random() > 0.5) {
  const y = 5;
}
console.log(y); // ReferenceError: y is not defined

```

However, variables created with **var** are not block-scoped, but only local to the function (or global scope) that the block resides within.

For example, the following code will log 5, because the scope of x is the global context (or the function context if the code is part of a function). The scope of x is not limited to the immediate if statement block.

```javascript
if (true) {
  var x = 5;
}
console.log(x); // x is 5
```

### Variable hoisting (important)

- **var**-declared variables are hoisted, meaning you can refer to the variable anywhere in its scope, even if its declaration isn't reached yet.
- You can see var declarations as being "lifted" to the top of its function or global scope. However, if you access a variable before it's declared, the value is always undefined, because only its declaration is hoisted, but not its initialization.

```javascript
console.log(x === undefined); // true
var x = 3;

(function () {
  console.log(x); // undefined
  var x = "local value";
})();
```

The above examples will be interpreted the same as: (actually how the code is interpreted)

```javascript
var x;
console.log(x === undefined); // true
x = 3;

(function () {
  var x;
  console.log(x); // undefined
  x = "local value";
})();
```

**(!)Because of hoisting, all var statements in a function should be placed as near to the top of the function as possible. This best practice increases the clarity of the code.**

Whether **let** and **const** are hoisted is a matter of definition debate.

Referencing the variable in the block before the variable declaration always results in a **ReferenceError**, because the variable is in a **"temporal dead zone"** from the start of the block until the declaration is processed.

```javascript
console.log(x); // ReferenceError
const x = 3;

console.log(y); // ReferenceError
let y = 3;
```

**Unlike var declarations, which only hoist the declaration but not its value, function declarations are hoisted entirely — you can safely call the function anywhere in its scope.**

### Global variables

Global variables are in fact properties of the global object.

In web pages, the global object is window, so you can set and access global variables using the window.variable syntax. In all environments, you can use the globalThis variable (which itself is a global variable) to access global variables.

Consequently, you can access global variables declared in one window or frame from another window or frame by specifying the window or frame name. For example, if a variable called phoneNumber is declared in a document, you can refer to this variable from an iframe as parent.phoneNumber.

### Constants

You can create a read-only, named constant with the const keyword. The syntax of a constant identifier is the same as any variable identifier: it must start with a letter, underscore, or dollar sign ($), and can contain alphabetic, numeric, or underscore characters.

```javascript
const PI = 3.14; // legal
const _PI = 3.142; // legal
const $PI = 3.142; // legal
```

- A constant cannot change value through assignment or be re-declared while the script is running.
- It must be initialized to a value.
- The scope rules for constants are the same as those for let block-scope variables.
- **You cannot declare a constant with the same name as a function or variable in the same scope.**

For example:

```javascript
// THIS WILL CAUSE AN ERROR
function f() {}
const f = 5;

// THIS WILL CAUSE AN ERROR TOO
function f() {
  const g = 5;
  var g;
}
-------------------------------------

const someVarName = 99;

function someVarName () { // throws error

}

for () {
  let someVarName = "2034sdsdf" // throws error
}
```

**(Important)**
However, const only prevents re-assignments, but doesn't prevent mutations. The properties of objects assigned to constants are not protected, so the following statement is executed without problems.

```javascript
const a = 99;

a = 69; // throws error (protected)

const MY_OBJECT = { key: "value" };
MY_OBJECT.key = "otherValue"; (not protected)
```

**(Important)**
Also, the contents of an array are not protected, so the following statement is executed without problems.

```javascript
const MY_ARRAY = ["HTML", "CSS"];
MY_ARRAY.push("JAVASCRIPT");
console.log(MY_ARRAY); // ['HTML', 'CSS', 'JAVASCRIPT'];

```

## **Data structures and types**

## Data types

The latest ECMAScript standard defines eight data types:

Seven data types that are primitives:

- Boolean. true and false.
- null. A special keyword denoting a null value. (Because JavaScript is case-sensitive, null is not the same as Null, NULL, or any other variant.)
- undefined. A top-level property whose value is not defined.
- Number. An integer or floating point number. For example: 42 or 3.14159.
- BigInt. An integer with arbitrary precision. For example: 9007199254740992n.
- String. A sequence of characters that represent a text value. For example: "Howdy".
- Symbol. A data type whose instances are unique and immutable.
- Object (non primitives)

Although these data types are relatively few, they enable you to perform useful operations with your applications. Functions are the other fundamental elements of the language. While functions are technically a kind of object, you can think of objects as named containers for values, and functions as procedures that your script can perform.

## Data type conversion (Important Note)

JavaScript is a dynamically typed language. This means you don't have to specify the data type of a variable when you declare it. It also means that data types are automatically converted as-needed during script execution.

So, for example, you could define a variable as follows:

```javascript
let answer = 42;

// And later, you could assign the same variable a string value, for example:

answer = "Thanks for all the fish!";

```

Because JavaScript is dynamically typed, this assignment does not cause an error message.

## Numbers and the '+' operator

In expressions involving numeric and string values with the + operator, JavaScript converts numeric values to strings. For example, consider the following statements:

```javascript
x = "The answer is " + 42; // "The answer is 42"
y = 42 + " is the answer"; // "42 is the answer"
z = "37" + 7; // "377"


// With all other operators, JavaScript does not convert numeric values to strings. For example:

// Observe 

"37" - 7; // 30
"37" * 7; // 259
```

## Converting strings to numbers

In the case that a value representing a number is in memory as a string, there are methods for conversion.

- parseInt()
- parseFloat()

parseInt only returns whole numbers, so its use is diminished for decimals.

```javascript
parseInt("101", 2); // 5

```

An alternative method of retrieving a number from a string is with the + (unary plus) operator:

```javascript
"1.1" + "1.1" // '1.11.1'
(+"1.1") + (+"1.1"); // 2.2
// Note: the parentheses are added for clarity, not required.

```
