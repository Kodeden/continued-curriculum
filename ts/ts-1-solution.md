# Challenge 1 Solution

**⚠️ DO NOT LOOK AT THE SOLUTION UNTIL YOU HAVE TRIED THIS YOURSELF!**
**⚠️ DO NOT JUST COPY AND PASTE THIS CODE! YOU WILL NOT LEARN PROPERLY!**

```ts
export function greet(personName: string): string {
  return "Hello, " + personName;
}
```

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
