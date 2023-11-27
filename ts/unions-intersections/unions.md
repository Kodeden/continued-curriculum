# Unions

## Introduction

Unions are a way to combine multiple types into one. They are used to describe values that can be one of several types. For example, a function that can take a string or a number:

```ts
function printId(id: number | string) {
  console.log(`Your ID is: ${id}`);
}
```

The syntax for unions is a single pipe (`|`). You can think of it as the word "or" in English. The type `number | string` means "a value that is either a number or a string". However, don't get it 😕 with `||` from JS!

`||` is used in JS code. `|` is used in type annotations - TS only!

## Using a Union in our `Person` Interface

Existing code for Person interface and greet function:

```ts
interface Address {
  street: string;
  city: string;
  state: string;
  zip: number;
}

export interface Person {
  readonly id: number;
  firstName: string;
  lastName: string;
  age: number;
  address: Address;
  hobbies?: string[];
}

export function greet(personName: Person): string {
  return `Hello, ${personName.firstName} ${personName.lastName}!`;
}

const me: Person = {
  id: 1,
  firstName: "John",
  lastName: "Doe",
  age: 42,
  address: {
    street: "123 Fake St",
    city: "Springfield",
    state: "IL",
    zip: 62701,
  },
};

console.log(greet(me));
```

---

We want to add a new property, addressType, to our Address interface. This property should only accept specific string values. Here's how we can enforce this with a union type:

```ts
type AddressType = "Home" | "Work" | "Other";

interface Address {
  street: string;
  city: string;
  state: string;
  zip: number;
  addressType: AddressType; // New property using union type
}
```

Note that we have to use `type` keyword instead of `interface` keyword to define a union type.

## Challenge - 🚗

Go back to `src/vehicles.ts` and add a new property to the `Vehicle` interface called `type` which is of type `VehicleType`. `VehicleType` should be a union of the following strings: `"car"`, `"truck"`, `"suv"`, `"van"`, `"motorcycle"`, `"boat"`, `"plane"`, `"spaceship"`, `"other"`. Then, modify the `describeVehicle` function to include the new property in the returned string.

As usual, `add` and `commit` (and `push`) your work and share with your instructor via Slack DM.

---

[Next ➡️ Intersections](./intersections.md)
