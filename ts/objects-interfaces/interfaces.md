# Interface

If you haven't already, add and commit the code you already did as we are going to update it here to use an **interface**.

## Recap

Specifying types 🏷️ is akin to writing a contract or passing laws about what **type of data** is allowed where. In the world of TS, similar to _1984,_ all of the citizens or code is under constant surveillance. The compiler is the **thought police** and will not allow you to break the rules.

Unlike _1984,_ the compiler does not have an insatiable desire for control and power. It is just trying to help you write better code. It is your friend. It is your ally. It is your **comrade** (like Big Brother) ;).

Previously we enforced a type 🏷️ rule for our **function parameter.** We made sure that only a **string** could be passed to the `greet` function. Any attempt to pass in another type would result in a compile error.

In that case the annotation: `: string` was added to the function parameter and that was it. As expected, simple enough for **primitive types**.

Of course, most of the real work we do is using **objects**.

## Use Interfaces to Type Objects

Objects are quite flexible. To set up a 'contract' for an object, we use an **interface**. An interface is a **custom type** that we define.

Let's create an interface for our `Person` object.

```ts
interface Person {
  firstName: string;
  lastName: string;
  age: number;
}
```

The above **interface** defines a **custom type** called `Person`. We typically use **PascalCase** for interface names.

It has three properties: `firstName`, `lastName`, and `age`. Each of these properties has a **type annotation**. The `firstName` and `lastName` properties are both **strings** and the `age` property is a **number**.

You can add this interface to the top of your `index.ts` file. In larger projects, where types 🏷️ get used in various parts of the code, it is common to put them in a separate file and import them.

### Challenge

Use the interface in the `greet` function. Update the function to take a `Person` as a parameter. Then update the function body to use the `firstName` and `lastName` properties of the `Person` object.

---

**⚠️ DO NOT LOOK AT THE SOLUTION UNTIL YOU HAVE TRIED THIS YOURSELF!**

[Solution](./solution-1.md)
