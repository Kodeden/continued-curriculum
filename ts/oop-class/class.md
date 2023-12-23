# Have Some `class`

## Interfaces (Review)

An interface in TypeScript is a way to define the shape of an object. It can include a combination of method signatures and properties.

```ts
interface Person {
  firstName: string;
  lastName: string;
  sayHello(): string;
}
```

## Classes

In JS, anytime you used the `new` keyword you were creating a specific instance (object) of a class. This is fairly rare in JS, but it's a common pattern in other languages. Fortunately, for these other programmers, JS introduced the `class` keyword.

Let it be known that `class` is just syntactic sugar for the constructor function pattern. It's not actually a new feature, but it's a lot easier to read and write.

And, if you haven't learned about the constructor function pattern, don't worry about it. You don't need to know it to use `class`.

If you're curious about Object Oriented Programming in JS, you can read more about it [here](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS).

Without further ado, here's a class:

```ts
class UserAccount {
  name: string;
  id: number;

  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
}
```

In this example, UserAccount class has properties name and id, and a constructor to initialize these properties when creating an instance of the class. That is, `new UserAccount("Murphy", 1)` creates a new instance (or object) of the UserAccount class.

## Classes with Interfaces

TypeScript allows classes to implement interfaces to ensure they adhere to a particular structure: `const user: User = new UserAccount("Murphy", 1);`

Here, `user` is declared as a type `User`(interface) and is assigned an instance of`UserAccount``(class). This enforces that`UserAccount`instances conform to the`User` interface.

---

## Challenge: Implementing Interfaces and Classes in TypeScript

### Objective

Reinforce your understanding of interfaces and classes in TypeScript by creating a simple implementation that adheres to a defined interface using a class.

### Challenge Details

1. **Define an Interface**:

   - Create an interface named `Vehicle` with the following properties:
     - `type`: string (e.g., "car", "truck")
     - `wheels`: number
     - `printDetails()`: a method that doesn't return anything.

2. **Create a Class**:

   - Implement a class named `Car` that adheres to the `Vehicle` interface.
   - It should have a constructor that accepts `type` and `wheels`.
   - Implement the `printDetails` method to log details about the car.

3. **Instantiate and Test (Manually is Fine)**:
   - Create an instance of the `Car` class.
   - Call the `printDetails` method to verify it works as expected.

#### Example Implementation

```typescript
// Your interface definition here
// Your class definition here

// Example instantiation and method call
const myCar = new Car("sedan", 4);
myCar.printDetails();
```
