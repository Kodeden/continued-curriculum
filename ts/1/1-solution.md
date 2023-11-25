# Challenge 1 Solution

**⚠️ DO NOT LOOK AT THE SOLUTION UNTIL YOU HAVE TRIED THIS YOURSELF!**
**⚠️ DO NOT JUST COPY AND PASTE THIS CODE! YOU WILL NOT LEARN PROPERLY!**

---

## Solution

```ts
export function greet(personName: string): string {
  return "Hello, " + personName;
}
```

We specified that the parameter `personName` is a `string` and that the function returns a `string`. `(personName: string): string`. The first `string` is the type of the parameter and the second `string` is the return type.

## Test ✅

```ts
import { expect, test } from "vitest";
import { greet } from "./index.js";

test("greet function should return the correct greeting", () => {
  const personName = "John";
  const expectedGreeting = "Hello, John";
  const result = greet(personName);
  expect(result).toBe(expectedGreeting);
});
```
