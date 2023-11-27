# TS Objects

We'll come back to our interface. Before we bother with it let's look at **implicitly typed objects**.

## Implicitly Typed Objects

We can create an object without explicitly defining its type. We can do this by assigning it to a variable and then assigning values to its properties.

[Video](https://somup.com/c0XTbQgzWO)

## Explicitly Typed Objects

Generally speaking, especially when learning JS, it's best to just be explicit for all of your data types. Case and point, you want to do: `const me: Person =` instead of `const me =`.

[Video](https://somup.com/c0XTbFgzW5)

### Additional 🎶

Understand how TypeScript's type system works, especially with respect to `const` assertions and object types.

1. **First Code Block (with `Person` type)**:

   ```typescript
   export interface Person {
     firstName: string;
     lastName: string;
     age: number;
   }

   const me: Person = {
     firstName: "John",
     lastName: "Doe",
     age: 42,
   } as const;

   me.firstName = "Jane";
   ```

   In this snippet, you're declaring `me` as a constant of type `Person`. The `Person` interface declares that `firstName`, `lastName`, and `age` are mutable properties (since they're not marked as `readonly`).

   The `as const` assertion here is somewhat misleading. It doesn't affect the mutability of `me` because the type of `me` is explicitly declared as `Person`, which takes precedence over the `as const` assertion. Therefore, TypeScript allows mutation of `firstName`.

2. **Second Code Block (without explicit type)**:

   ```typescript
   const me = {
     firstName: "John",
     lastName: "Doe",
     age: 42,
   } as const;

   me.firstName = "Jane";
   ```

   In this case, `me` is declared without an explicit type, so the `as const` assertion has a more significant effect. It effectively makes all properties of `me` deeply readonly. This means you cannot change `firstName`, `lastName`, or `age` after the object is created.

The key difference is how TypeScript interprets the `as const` assertion in the context of an explicitly typed variable versus an implicitly typed one. When the variable is explicitly typed (as in the first case), the explicit type definition (the `Person` interface) dictates the mutability of its properties, overriding the `as const` assertion. In the second case, without an explicit type, `as const` dictates the entire type of the variable, making all of its properties readonly.

## Challenge - 🚗

Before we continue, let's make sure you understand how to use interfaces. Create an interface for a `Car` object. It should have the following properties:

- `make` - string
- `model` - string
- `year` - number
- `color` - string
- `isElectric` - boolean

Then create a function called `describeCar` that takes a `Car` as a parameter and returns a string describing the car. For example, if the car is a 2019 Tesla Model 3, the function should return: `2019 Tesla Model 3`.

You can just create another file in `src` called `vehicles.ts`. You could then export that code and run it from `index.ts`. Or, just do: `node dist/vehicles.js` from the command line.

You can hold off on writing the unit test for this until later.

Be sure to commit and share your code with your instructor via Slack DM.

No solution is provided for this challenge. Just do it and submit it to your instructor **with** a brief explanation of what you did (e.g. video 📹).

---

[Next ➡️ Optional Properties](./optional-properties.md)
