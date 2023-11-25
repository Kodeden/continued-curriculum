# Interface 1 Solution

**⚠️ DO NOT LOOK AT THE SOLUTION UNTIL YOU HAVE TRIED THIS YOURSELF!**
**⚠️ DO NOT JUST COPY AND PASTE THIS CODE! YOU WILL NOT LEARN PROPERLY!**

---

## Solution

```ts
export function greet(person: Person): string {
  return "Hello, " + person.firstName + " " + person.lastName;
}
```

`(person: Person)` is the type annotation for the parameter. It says that the parameter `person` must be of type `Person`. The `Person` type is defined by the interface we created.

`: string` is the return type annotation. It says that the function must return a `string`.
