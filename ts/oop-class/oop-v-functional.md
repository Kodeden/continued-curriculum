# Embracing Functional Programming in JavaScript and TypeScript

## Introduction

JavaScript offers the flexibility to use both Object-Oriented Programming (OOP) and Functional Programming (FP). However, the modern trend and many advantages lean towards FP, especially in the context of web development and frameworks like React.

## Overview of Functional Programming

If you've used Array methods such as `map`, `filter`, and `reduce`, you've already used FP. These methods are pure functions that take an array as input and return a new array without modifying the original one (avoiding a mutation). They are using callbacks to achieve this, which is a common FP pattern.

Functional programming is possible in JS/TS because functions are considered as first-class citizens. This means that functions can be passed as arguments to other functions, returned from functions, and assigned to variables, just like any other data type.

For instance, the following code snippet assigns a function to a variable and then calls it:

```ts
const sayHello = () => console.log("Hello!");
sayHello(); // Hello!
```

We can also return a function from another function, resulting in a higher-order function:

```ts
const createCustomGreeter = (name: string) => {
  return () => console.log(`Hello ${name}!`);
};

const greet = createCustomGreeter("John");

greet(); // Hello John!
```

In fact, the example above creates a **closure**, which is a function that remembers the variables from the scope in which it was created. In this case, the `greet` function remembers the `name` variable from the `createCustomGreeter` function. `name` is **enclosed** in the `greet` function, hence the name closure.

And, perhaps the most common thing you have already done is to pass functions into other functions (callbacks):

```ts
const numbers = [1, 2, 3, 4, 5];

const double = (n: number) => n * 2;

const doubledNumbers = numbers.map(double);

console.log(doubledNumbers); // [2, 4, 6, 8, 10]
```

**Note**: The examples above should be mostly readable. If the code seems completely foreign, it's a good time to react out to your instructor via Slack for additional help.

All of these examples demonstrate the power of functions in JS/TS. However, FP is more than just using functions. It is a paradigm that emphasizes the use of pure functions and immutable data.

### Pure Functions

A pure function is a function that always returns the same output for the same input and has no side effects. This means that a pure function does not modify any data outside of its scope. For instance, the `double` function above is a pure function because it always returns the same output for the same input and does not modify any data outside of its scope. Again, `map`, `filter`, and `reduce` (among others) are also pure functions. They create new data instead of mutating the original data like `push`, `pop`, and `splice` (among others) do.

Again, if any of the aforementioned concepts are new to you, please reach out to your instructor via Slack for additional help.

### Immutability

Immutability is the concept of not changing data after it has been created. This is a core principle of FP and is achieved by using pure functions and avoiding mutations. For instance, the following code snippet mutates the `numbers` array by adding a new element to it:

```ts
const numbers = [1, 2, 3, 4, 5];

numbers.push(6);

console.log(numbers); // [1, 2, 3, 4, 5, 6]
```

On the other hand, the following code snippet creates a new array instead of mutating the original one:

```ts
const numbers = [1, 2, 3, 4, 5];

const newNumbers = [...numbers, 6];

console.log(newNumbers); // [1, 2, 3, 4, 5, 6]
console.log(numbers); // [1, 2, 3, 4, 5]
```

### Benefits of Functional Programming

- **Simplicity and Readability**: FP's focus on pure functions leads to more straightforward and predictable code.
- **Immutable Data**: Emphasizing immutability reduces bugs related to data changes.
- **Modularity and Reusability**: FP promotes breaking down problems into smaller, reusable functions.
- **Easier Testing and Debugging**: Pure functions are easier to test and debug as they have no side effects and depend only on their input.
- **Conciseness**: FP reduces the amount of code needed to solve a problem.
- **Composition**: FP encourages composing functions to create more complex functions.

And the list goes on, but these are some of the most important benefits of FP.

## Functional Programming in Modern Development

- **React and FP**: React, one of the most popular front-end libraries, encourages the use of functional components, showcasing the FP approach in action.
- **Evolution of Traditional OOP Languages**: Languages like Java and C# have introduced features like lambdas and streams, incorporating FP principles to offer more concise and readable code.

## Limited Role of OOP in Modern Development

### Basic Example

```ts
class Animal {
  name: string;

  constructor(name: string) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

let dog = new Animal("Dog");
dog.speak(); // Output: Dog makes a sound.
```

### Inheritance with `class` and `extends`

```ts
class Dog extends Animal {
  breed: string;

  constructor(name: string, breed: string) {
    super(name);
    this.breed = breed;
  }

  speak() {
    console.log(`${this.name}, the ${this.breed}, barks.`);
  }
}

let bulldog = new Dog("Buddy", "Bulldog");
bulldog.speak(); // Output: Buddy, the Bulldog, barks.
```

Although a deep dive into **inheritance,** is not the point, note that JS **does not** do 'class-based inheritance' like Java or C#. Instead, it uses **prototypal inheritance**. This is a subtle but important distinction. `class` is just syntactic sugar for prototypal inheritance. It's 'fake.'

### Legacy Codebases

Many codebases and libraries are written in OOP, and it is essential to understand OOP concepts to work with them. However, the trend is shifting towards FP, and many new libraries and frameworks are embracing FP.

The JavaScript ecosystem has increasingly adopted FP for its concise syntax and ability to simplify complex operations, making it apt for modern web development tasks.

### OOP Limitations

- **Complexity**: OOP can be complex and difficult to understand, especially for beginners.
- **Mutability**: OOP promotes mutable data, which can lead to bugs and unexpected behavior.
- **Side Effects**: OOP can lead to side effects, which can be difficult to debug. Here, a side effect is any change in the state of the program that is observable outside the called function other than its return value. It basically relates to mutations and impure functions.

The trend in JavaScript and TypeScript is increasingly favoring FP for its simplicity and alignment with the nature of web development. In fact, `class` was only introduced in ES6 to make JavaScript more familiar to developers coming from traditional OOP languages like Java and C#.

## Conclusion

While OOP focuses on objects with encapsulated data and methods, FP focuses on pure functions and immutable data. In our TypeScript journey, we will emphasize functional programming due to its growing popularity in the JavaScript ecosystem and its various benefits. However, we also acknowledge the importance of understanding OOP concepts, as they remain a significant part of many codebases and libraries. The goal is to equip you with a comprehensive understanding of TypeScript, enabling you to write efficient, clean, and modern code.

While we embrace Functional Programming in our TypeScript journey, we equip ourselves with a modern, efficient approach to web development. Understanding both FP and OOP enriches our skill set, allowing us to adapt to various coding environments and challenges. Remember, the goal is not just to learn a programming style but to understand the concepts and practices that make us versatile, effective developers in the ever-evolving world of web technology.
