# Nested Interfaces

In your `src/index.ts`, you should have code similar to the following:

```typescript
export interface Person {
  readonly id: number;
  firstName: string;
  lastName: string;
  age: number;
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
};

console.log(greet(me));
```

Feel free to copy/paste that if you don't - provided that you already went through the previous lessons and that this all looks familiar to you.

## Adding an Address

Interfaces can be nested. Modify the previous code as shown below:

```diff
diff --git a/src/index.ts b/src/index.ts
index 9802f54..19cae6f 100644
--- a/src/index.ts
+++ b/src/index.ts
@@ -1,8 +1,17 @@
+interface Address {
+  street: string;
+  city: string;
+  state: string;
+  zip: number;
+}
+
 export interface Person {
   readonly id: number;
   firstName: string;
   lastName: string;
   age: number;
+  address: Address;
+
   hobbies?: string[];
 }

@@ -15,6 +24,12 @@ const me: Person = {
   firstName: "John",
   lastName: "Doe",
   age: 42,
+  address: {
+    street: "123 Fake St",
+    city: "Springfield",
+    state: "IL",
+    zip: 62701,
+  },
 };

 console.log(greet(me));
```

As you can see, we added a new interface called `Address` and we added a new property to the `Person` interface called `address` which is of type `Address`.

## Challenge

Go back to `vehicles.ts`. Import the `Person` interface from `index.ts` and use it to add an `owner` property of the `Vehicle` interface. This property should be of type `Person`.

As usual add and commit your changes, and share with your instructor via Slack DM.
