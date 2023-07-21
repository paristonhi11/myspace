---
title: TypeScript Notes
---

# TypeScript

## TypeScript WW&H

TypeScript is an open-source programming language developed by Microsoft. It is a statically typed superset of JavaScript, which means it builds upon JavaScript by adding static typing features and other enhancements. TypeScript compiles down to plain JavaScript, allowing it to run on any JavaScript runtime.

Here are some key features of TypeScript:

1.  **Static Typing:** TypeScript introduces static typing, which allows you to specify types for variables, function parameters, and return values. It helps catch errors during development and provides better tooling support, such as code completion and refactoring.
2.  **Type Inference:** TypeScript has a powerful type inference system that can automatically infer the types of variables based on their initial values. This reduces the need for explicit type annotations and makes the language more expressive.
3.  **Interfaces and Classes:** TypeScript supports the concept of interfaces and classes, which are absent in standard JavaScript. Interfaces define contracts for objects, specifying the structure and types of their properties and methods. Classes enable object-oriented programming features like inheritance, encapsulation, and abstraction.
4.  **Enums:** TypeScript includes support for enumerations (enums), which allow you to define a set of named constant values. Enums make it easier to work with predefined sets of related values, providing more expressive code.
5.  **Generics:** TypeScript introduces generics, which enable the creation of reusable components that can work with different types. Generics allow you to define types and functions in a generic way, without specifying the specific type upfront.
6.  **Advanced JavaScript Features:** TypeScript supports the latest ECMAScript (JavaScript) features, even before they are fully supported by all browsers. This allows developers to leverage the latest JavaScript syntax and features while enjoying the benefits of static typing.

TypeScript is often used for large-scale JavaScript applications, where static typing can help catch errors early and improve code maintainability. It integrates well with popular JavaScript frameworks and libraries, providing enhanced tooling and developer experience.

### Statically Typed

TypeScript supports several built-in data types, which are similar to JavaScript's data types. Here are the common data types in TypeScript:

1. **Boolean**: Represents a logical value that can be either `true` or `false`.
2. **Number**: Represents numeric values, including integers and floating-point numbers. TypeScript supports both decimal and hexadecimal notation, as well as special values like `NaN` and `Infinity`.

3. **String**: Represents a sequence of characters. It can be enclosed in single quotes (`'`) or double quotes (`"`).

4. **Array**: Represents an ordered collection of elements of the same type. In TypeScript, arrays can be defined using the `type[]` syntax or the generic `Array<type>` syntax.

5. **Tuple**: Represents an array with a fixed number of elements, where each element can have its own type. The types of the elements are known and fixed at compile-time.

6. **Enum**: Represents a set of named constants. Enums allow you to define a custom set of values with descriptive names.

7. **Any**: Represents a dynamic or unknown type. Variables of type `any` can hold values of any type, and TypeScript doesn't perform type-checking on them.

8. **Void**: Represents the absence of a value. It is commonly used as the return type of functions that don't return a value.

9. **Null and Undefined**: Represents the absence of an assigned value. `null` is a value that indicates the intentional absence of any object value, while `undefined` indicates the absence of an assigned value.

10. **Object**: Represents a non-primitive type. It refers to any value that is not of the primitive types (`boolean`, `number`, `string`, `symbol`, `null`, or `undefined`).

11. **Union**: Represents a type that can hold values of multiple types. It is denoted using the `|` operator between type annotations.

12. **Intersection**: Represents a type that combines multiple types. It is denoted using the `&` operator between type annotations.

Additionally, TypeScript allows you to define custom types using interfaces, classes, and type aliases, enabling you to create more complex and structured data types based on your application's needs.

It's worth noting that TypeScript is a superset of JavaScript, so you can use all the standard JavaScript data types in TypeScript as well.

```typescript
// Boolean
let isCompleted: boolean = false;

// Number
let age: number = 25;
let pi: number = 3.14;

// String
let name: string = "John Doe";

// Array
let numbers: number[] = [1, 2, 3, 4, 5];
let fruits: Array<string> = ["apple", "banana", "orange"];

// Tuple
let person: [string, number] = ["John", 25];

// Enum
enum Color {
  Red,
  Green,
  Blue,
}
let chosenColor: Color = Color.Blue;

// Any
let dynamicValue: any = "Hello";
dynamicValue = 10;

// Void
function sayHello(): void {
  console.log("Hello!");
}

// Null and Undefined
let nullValue: null = null;
let undefinedValue: undefined = undefined;

// Object
let personObject: object = { name: "John", age: 25 };

// Union
let phoneNumber: string | number = "1234567890";

// Intersection
type Greeting = { message: string };
type Name = { name: string };
let personInfo: Greeting & Name = { message: "Hello", name: "John" };

// Array of Objects
interface Book {
  title: string;
  author: string;
}

let books: Book[] = [
  { title: "The Great Gatsby", author: "F. Scott Fitzgerald" },
  { title: "To Kill a Mockingbird", author: "Harper Lee" },
  { title: "1984", author: "George Orwell" },
];
```

In the above example, we declare variables with explicit type annotations to demonstrate the static typing features of TypeScript. Each variable is assigned a value consistent with its respective data type.

- `isCompleted` is of type `boolean`.
- `age` and `pi` are of type `number`.
- `name` is of type `string`.
- `numbers` is an array of `number`, while `fruits` is an array of `string`.
- `person` is a tuple with the first element being of type `string` and the second element of type `number`.
- `chosenColor` is an enum variable of type `Color`.
- `dynamicValue` is of type `any`, allowing it to hold values of any type.
- `sayHello` is a function that returns `void`.
- `nullValue` and `undefinedValue` are variables explicitly assigned `null` and `undefined` values, respectively.
- `personObject` is an object of type `object`.
- `phoneNumber` is a union type that can hold values of either `string` or `number`.
- `personInfo` is an intersection type that combines the properties of `Greeting` and `Name` types.

These examples showcase the usage of different static types available in TypeScript.

When the TypeScript code you provided is compiled to JavaScript, it will look like this:

```javascript
// Boolean
let isCompleted = false;

// Number
let age = 25;
let pi = 3.14;

// String
let name = "John Doe";

// Array
let numbers = [1, 2, 3, 4, 5];
let fruits = ["apple", "banana", "orange"];

// Tuple
let person = ["John", 25];

// Enum
var Color;
(function (Color) {
  Color[(Color["Red"] = 0)] = "Red";
  Color[(Color["Green"] = 1)] = "Green";
  Color[(Color["Blue"] = 2)] = "Blue";
})(Color || (Color = {}));
let chosenColor = Color.Blue;

// Any
let dynamicValue = "Hello";
dynamicValue = 10;

// Void
function sayHello() {
  console.log("Hello!");
}

// Null and Undefined
let nullValue = null;
let undefinedValue = undefined;

// Object
let personObject = { name: "John", age: 25 };

// Union
let phoneNumber = "1234567890";

// Intersection
let personInfo = { message: "Hello", name: "John" };

// Array of Objects
let books = [
  { title: "The Great Gatsby", author: "F. Scott Fitzgerald" },
  { title: "To Kill a Mockingbird", author: "Harper Lee" },
  { title: "1984", author: "George Orwell" },
];
```

The TypeScript code is transpiled into JavaScript while retaining the same functionality. The resulting JavaScript code omits the type annotations as JavaScript is a dynamically typed language, unlike TypeScript, which enforces static typing during compilation.

### Type inference

Type inference is a feature in TypeScript that allows the compiler to automatically determine the type of a variable based on its initialization value or how it is used within the code. This means that you don't always have to explicitly specify the types of variables because TypeScript can infer them for you.

Here's an example to demonstrate type inference:

```typescript
let age = 25; // Type inference: number
let name = "John Doe"; // Type inference: string
let isCompleted = false; // Type inference: boolean

function addNumbers(a: number, b: number) {
  return a + b;
}

let result = addNumbers(5, 10); // Type inference: number
```

In this example, we declare variables `age`, `name`, and `isCompleted` without explicitly specifying their types. TypeScript infers their types based on their initialization values:

- `age` is assigned the value `25`, so TypeScript infers its type as `number`.
- `name` is assigned the value `"John Doe"`, so TypeScript infers its type as `string`.
- `isCompleted` is assigned the value `false`, so TypeScript infers its type as `boolean`.

In the `addNumbers` function, the parameters `a` and `b` are explicitly annotated as `number` types. When we call the `addNumbers` function and assign the result to the variable `result`, TypeScript infers the type of `result` as `number` because the function returns the sum of two numbers.

Type inference helps reduce the verbosity of code by eliminating the need for explicit type annotations in many cases. However, it's still good practice to provide explicit type annotations in situations where type inference may not produce the expected or desired types, or when the code is more readable and maintainable with explicit type declarations.

### Interfaces and Classes

In TypeScript, interfaces and classes are key constructs that allow you to define custom types and create reusable and structured code. Let's explain interfaces and classes with examples:

**Interfaces:**

Interfaces define the structure of an object and can be used to enforce a specific shape or contract that objects should adhere to. They specify the properties and methods that an object must have. Here's an example:

```typescript
interface Person {
  name: string;
  age: number;
  greet(): void;
}

class Student implements Person {
  constructor(public name: string, public age: number) {}

  greet() {
    console.log(
      `Hello, my name is ${this.name} and I'm ${this.age} years old.`
    );
  }
}

const john: Person = new Student("John", 25);
john.greet(); // Output: Hello, my name is John and I'm 25 years old.
```

In this example, we define an interface called `Person`, which requires objects to have properties `name` (of type `string`), `age` (of type `number`), and a method `greet` (returning `void`). We then create a class `Student` that implements the `Person` interface. The `Student` class must have the same properties and method as specified in the `Person` interface.

We create an instance of the `Student` class, `john`, and assign it to a variable of type `Person`. This demonstrates that an object of the `Student` class can be treated as a `Person` type. We can then call the `greet` method on the `john` object, which logs a greeting to the console.

Interfaces allow you to define contracts and ensure that objects adhere to a specific structure, promoting code reusability and maintainability.

**Classes:**

Classes are blueprint/templates for creating objects. They encapsulate data (properties) and behavior (methods) into a single unit. Here's an example:

```typescript
class Animal {
  constructor(public name: string) {}

  makeSound() {
    console.log("Making a sound...");
  }
}

class Dog extends Animal {
  constructor(name: string) {
    super(name);
  }

  makeSound() {
    console.log("Barking!");
  }
}

const dog = new Dog("Buddy");
console.log(dog.name); // Output: Buddy
dog.makeSound(); // Output: Barking!
```

In this example, we define a base class `Animal` with a constructor that accepts a `name` parameter and a `makeSound` method. We then create a derived class `Dog` that extends the `Animal` class. The `Dog` class inherits the properties and methods of the `Animal` class and can also define its own.

We create an instance of the `Dog` class, `dog`, and provide a name "Buddy" to the constructor. We can access the `name` property and call the `makeSound` method on the `dog` object.

Classes allow you to create objects with specific characteristics and behaviors, enabling code organization, reusability, and the ability to create instances of those objects.

Interfaces and classes are powerful constructs in TypeScript that facilitate the creation of well-structured and reusable code by enforcing contracts and defining object blueprints.

### Enums

Certainly! Here's another example of how enums can be used:

```typescript
enum DayOfWeek {
  Monday = "MON",
  Tuesday = "TUE",
  Wednesday = "WED",
  Thursday = "THU",
  Friday = "FRI",
  Saturday = "SAT",
  Sunday = "SUN",
}

function getWeekendMessage(day: DayOfWeek) {
  if (day === DayOfWeek.Saturday || day === DayOfWeek.Sunday) {
    return "It's the weekend! Enjoy your time off!";
  } else {
    return "It's a weekday. Keep up the good work!";
  }
}

console.log(getWeekendMessage(DayOfWeek.Monday)); // Output: It's a weekday. Keep up the good work!
console.log(getWeekendMessage(DayOfWeek.Saturday)); // Output: It's the weekend! Enjoy your time off!
```

In this example, we define an enum called `DayOfWeek`. Each constant in the enum is assigned a string value that represents the abbreviated name of the day.

The `getWeekendMessage` function takes a parameter `day` of type `DayOfWeek` and checks if the day is a weekend day (`Saturday` or `Sunday`). Depending on the day provided, it returns a corresponding message.

We then invoke the `getWeekendMessage` function with different days of the week. For `DayOfWeek.Monday`, it returns the message indicating that it's a weekday. For `DayOfWeek.Saturday`, it returns the message indicating that it's the weekend.

By using an enum, we can define and reference days of the week with meaningful names (`Monday`, `Tuesday`, etc.) rather than using plain strings or numbers. This enhances code readability and makes it easier to work with and reason about different days of the week.

### Generics

Certainly! Here's a more detailed example of generics in TypeScript:

```typescript
class Box<T> {
  private items: T[] = [];

  addItem(item: T) {
    this.items.push(item);
  }

  getItem(index: number): T {
    return this.items[index];
  }

  getItems(): T[] {
    return this.items;
  }
}

// Creating a Box of strings
const stringBox = new Box<string>();
stringBox.addItem("Apple");
stringBox.addItem("Banana");
stringBox.addItem("Orange");

console.log(stringBox.getItems()); // Output: ["Apple", "Banana", "Orange"]
console.log(stringBox.getItem(1)); // Output: "Banana"

// Creating a Box of numbers
const numberBox = new Box<number>();
numberBox.addItem(1);
numberBox.addItem(2);
numberBox.addItem(3);

console.log(numberBox.getItems()); // Output: [1, 2, 3]
console.log(numberBox.getItem(2)); // Output: 3
```

In this example, we have a `Box` class that can hold and retrieve items of any type `T`.

The `Box` class is defined with a type parameter `<T>`, which serves as a placeholder for the type of items stored in the box.

The `Box` class has three methods:

- `addItem`: Takes an argument of type `T` and adds it to the `items` array.
- `getItem`: Takes an index as an argument and returns the item at that index, of type `T`.
- `getItems`: Returns the array of items, of type `T[]`.

We create an instance of `Box<string>` and add three string items to it: "Apple", "Banana", and "Orange". We then call `getItems` to retrieve all the items in the string box and `getItem(1)` to retrieve the item at index 1, which is "Banana".

Similarly, we create an instance of `Box<number>` and add three number items: 1, 2, and 3. We call `getItems` to retrieve all the items in the number box and `getItem(2)` to retrieve the item at index 2, which is 3.

By using generics, we create a flexible `Box` class that can work with different types of items while maintaining type safety. The type parameter `T` allows the `Box` class to be reusable and handle various types without sacrificing type checking.

### Advanced JavaScript Feature

In TypeScript, closures are utilized in a similar manner as in JavaScript. TypeScript's support for closures allows you to create functions that have access to variables from their containing scope, even after the scope has exited.

TypeScript provides type inference and type checking capabilities to ensure that closures operate with the correct types of variables. Here's an example in TypeScript that demonstrates the usage of closures:

```typescript
function createMultiplier(factor: number) {
  return function (number: number): number {
    return factor * number;
  };
}

const double = createMultiplier(2);
console.log(double(5)); // Output: 10

const triple = createMultiplier(3);
console.log(triple(5)); // Output: 15
```

In this example, we have a function `createMultiplier` that takes a `factor` parameter and returns an inner function. The inner function takes a `number` parameter and returns the product of the `factor` and `number`.

We assign the returned function from `createMultiplier(2)` to the `double` variable and invoke it with the argument `5`. It multiplies `5` by `2` and returns the result `10`.

Similarly, we assign the returned function from `createMultiplier(3)` to the `triple` variable and invoke it with the argument `5`. It multiplies `5` by `3` and returns the result `15`.

TypeScript infers the types of the parameters and return values based on the provided arguments and the defined function signature. In this case, the inner function has a parameter of type `number` and returns a value of type `number`.

By utilizing closures in TypeScript, you can create functions that encapsulate data from their outer scopes and still benefit from TypeScript's type checking and type inference capabilities. This allows for type-safe and reusable code that maintains access to variables from its surrounding context.

## Need of Typescript

There are several reasons why TypeScript is widely adopted and valuable for building modern JavaScript applications:

1. **Type Safety**: TypeScript adds static typing to JavaScript, enabling early detection of type-related errors during development. It helps catch common mistakes, such as assigning incorrect types to variables or invoking functions with the wrong arguments. The static type checking provided by TypeScript helps improve code quality and reduces runtime errors.

2. **Enhanced Developer Experience**: TypeScript enhances the developer experience through features like autocompletion, intelligent code navigation, and refactoring support. With its rich language services, TypeScript-enabled editors provide real-time feedback, suggestions, and error highlighting, making it easier to write and maintain code.

3. **Improved Code Maintainability**: TypeScript promotes scalability and maintainability by introducing features like interfaces, classes, and modules. These features provide a way to organize and structure code, enforce contracts, and facilitate code reuse. TypeScript's tooling support also helps with large codebases, making it easier to refactor and navigate through complex projects.

4. **ESNext Features and Compatibility**: TypeScript is a superset of JavaScript and supports the latest ECMAScript (ESNext) features. It allows developers to write code using the latest JavaScript syntax and features, which are then transpiled into backwards-compatible JavaScript versions to run in older environments. This means you can leverage modern language features while ensuring compatibility with older browsers or platforms.

5. **Better Collaboration**: TypeScript improves collaboration among team members, especially in larger projects, by providing explicit type annotations and clear interfaces. This makes it easier for developers to understand and consume code written by others. It also enhances the onboarding process for new team members, as the types act as documentation and provide insights into the expected behavior of the code.

6. **Ecosystem and Tooling**: TypeScript has a vibrant ecosystem with excellent tooling support. It integrates well with popular frameworks and libraries like React, Angular, and Node.js, offering enhanced TypeScript-specific features and optimizations. The TypeScript compiler (`tsc`) and other development tools provide powerful options for code analysis, linting, testing, and bundling, contributing to a smooth development workflow.

Overall, TypeScript offers the benefits of static typing, improved developer experience, code maintainability, compatibility, collaboration, and a rich ecosystem. It provides a strong foundation for building robust, scalable, and maintainable JavaScript applications, making it a popular choice among developers and organizations.

## TypeScript Tic-tac-toe Game

Sure! Here's an example of a simple Tic Tac Toe game using HTML, CSS, and TypeScript:

HTML:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Tic Tac Toe</title>
    <link rel="stylesheet" type="text/css" href="styles.css" />
  </head>
  <body>
    <h1>Tic Tac Toe</h1>
    <div id="board">
      <div class="cell" onclick="makeMove(0)"></div>
      <div class="cell" onclick="makeMove(1)"></div>
      <div class="cell" onclick="makeMove(2)"></div>
      <div class="cell" onclick="makeMove(3)"></div>
      <div class="cell" onclick="makeMove(4)"></div>
      <div class="cell" onclick="makeMove(5)"></div>
      <div class="cell" onclick="makeMove(6)"></div>
      <div class="cell" onclick="makeMove(7)"></div>
      <div class="cell" onclick="makeMove(8)"></div>
    </div>
    <button onclick="resetBoard()">Reset</button>

    <script src="script.js"></script>
  </body>
</html>
```

CSS (styles.css):

```css
#board {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
  margin-bottom: 10px;
}

.cell {
  width: 100px;
  height: 100px;
  background-color: lightgray;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 40px;
  cursor: pointer;
}

button {
  font-size: 20px;
  padding: 10px 20px;
}

h1 {
  text-align: center;
}
```

TypeScript (script.ts):

```typescript
enum Player {
  None = '',
  X = 'X',
  O = 'O',
}

let currentPlayer: Player = Player.X;
let board: Player[] = Array(9).fill(Player.None);

function makeMove(cellIndex: number) {
  if (board[cellIndex] !== Player.None) {
    return;
  }

  board[cellIndex] = currentPlayer;

  const cell = document.getElementsByClassName('cell')[cellIndex];
  cell.textContent = currentPlayer;

  if (checkWin(currentPlayer)) {
    alert(`${currentPlayer} wins!`);
    resetBoard();
    return;
  }

  if (board.every(cell => cell !== Player.None)) {
    alert("It's a tie!");
    resetBoard();
    return;
  }

  currentPlayer = currentPlayer === Player.X ? Player.O : Player.X;
}

function checkWin(player: Player): boolean {
  const winningCombinations = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8], // Rows
    [0, 3, 6], [1, 4, 7], [2, 5, 8], // Columns
    [0, 4, 8], [2, 4, 6] // Diagonals
  ];

  return winningCombinations.some(combination => {
    const [a, b, c] = combination;
    return (
      board[a] === player &&
      board[b] === player &&
      board[c] === player
    );
  });
}

function resetBoard() {
  currentPlayer = Player.X;
  board = Array(9).fill(Player.None);

  const cells = document.getElementsByClassName('cell');

```

Here is the Javascript Compilation of Ts code:

```javascript

"use strict";
var Player;
(function (Player) {
    Player["None"] = "";
    Player["X"] = "X";
    Player["O"] = "O";
})(Player || (Player = {}));
let currentPlayer = Player.X;
let board = Array(9).fill(Player.None);
function makeMove(cellIndex) {
    if (board[cellIndex] !== Player.None) {
        return;
    }
    board[cellIndex] = currentPlayer;
    const cell = document.getElementsByClassName('cell')[cellIndex];
    cell.textContent = currentPlayer;
    if (checkWin(currentPlayer)) {
        alert(`${currentPlayer} wins!`);
        resetBoard();
        return;
    }
    if (board.every(cell =%3E cell !== Player.None)) {
        alert("It's a tie!");
        resetBoard();
        return;
    }
    currentPlayer = currentPlayer === Player.X ? Player.O : Player.X;
}
function checkWin(player) {
    const winningCombinations = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8],
        [0, 3, 6], [1, 4, 7], [2, 5, 8],
        [0, 4, 8], [2, 4, 6] // Diagonals
    ];
    return winningCombinations.some(combination => {
        const [a, b, c] = combination;
        return (board[a] === player &&
            board[b] === player &&
            board[c] === player);
    });
}
function resetBoard() {
    currentPlayer = Player.X;
    board = Array(9).fill(Player.None);
    const cells = document.getElementsByClassName('cell');
})
```

Sure! Here's an example of a Hangman game implemented in TypeScript that you can play in the terminal:

```typescript
import * as readline from "readline";

const words: string[] = [
  "hangman",
  "javascript",
  "typescript",
  "openai",
  "programming",
];

const randomWord: string = words[Math.floor(Math.random() * words.length)];
const guessedLetters: Set<string> = new Set();
let remainingAttempts: number = 6;

function displayWord(): void {
  let displayedWord: string = "";
  for (const char of randomWord) {
    if (guessedLetters.has(char)) {
      displayedWord += char;
    } else {
      displayedWord += "_";
    }
  }
  console.log(`Word: ${displayedWord}`);
}

function displayHangman(): void {
  const hangmanStages: string[] = [
    `
    ________
    |      |
    |      
    |       
    |      
    |      
    |
    `,
    `
    ________
    |      |
    |      O
    |       
    |      
    |      
    |
    `,
    `
    ________
    |      |
    |      O
    |      |
    |      
    |      
    |
    `,
    `
    ________
    |      |
    |      O
    |     /|
    |      
    |      
    |
    `,
    `
    ________
    |      |
    |      O
    |     /|\\
    |      
    |      
    |
    `,
    `
    ________
    |      |
    |      O
    |     /|\\
    |     /
    |      
    |
    `,
    `
    ________
    |      |
    |      O
    |     /|\\
    |     / \\
    |      
    |
    `,
  ];

  console.log(hangmanStages[6 - remainingAttempts]);
}

function makeGuess(): void {
  const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
  });

  rl.question("Enter a letter: ", (letter: string) => {
    const guessedLetter = letter.trim().toLowerCase();

    if (!guessedLetter || !guessedLetter.match(/^[a-z]$/)) {
      console.log("Invalid input! Please enter a single letter.");
    } else if (guessedLetters.has(guessedLetter)) {
      console.log("You already guessed that letter. Try again!");
    } else {
      guessedLetters.add(guessedLetter);

      if (randomWord.includes(guessedLetter)) {
        console.log("Correct guess!");
      } else {
        remainingAttempts--;
        console.log("Incorrect guess!");
      }
    }

    rl.close();
    playGame();
  });
}

function playGame(): void {
  console.log("\n------------------------------------");
  displayWord();
  displayHangman();
  console.log(`Remaining attempts: ${remainingAttempts}`);
  console.log(`Guessed letters: ${[...guessedLetters].join(", ")}`);

  if (remainingAttempts === 0) {
    console.log("\nGame Over! You ran out of attempts.");
    console.log(`The word was: ${randomWord}`);
  } else if ([...randomWord].every((char) => guessedLetters.has(char))) {
    console.log("\nCongratulations! You guessed the word correctly!");
    console.log(`The word was: ${randomWord}`);
  } else {
    makeGuess();
  }
}

console.log("Welcome to Hangman - Terminal Version");
console.log("Guess the word by entering one letter at a time.");

playGame();
```

To run the Hangman game, save the code to a TypeScript file (e.g.,

`hangman.ts`), and then compile it using the TypeScript compiler:

```
tsc hangman.ts
```

After compilation, you can run the game by executing the generated JavaScript file:

```
node hangman.js
```

The game will prompt you to enter a letter to make a guess. Keep making guesses until you either guess the word correctly or run out of attempts. The game will display the hangman figure, the current status of the word, the remaining attempts, and the guessed letters after each guess.

Enjoy playing Hangman in the terminal!

# Angular
