# Adding Vitest

This isn't directly TS-centric, but let's add Vitest to our template repo. You're likely familiar with Vitest, a test runner that is essentially a better and faster version of Jest. It's also the test runner that is used in the EduFlow curriculum. If this doesn't sound familiar, ask your instructor about it.

---

1. `npm install -D vite vitest @vitest/ui`.
1. Add the following `"scripts"` to `package.json`:

```json
"scripts": {
    "build": "tsc --watch",
    "coverage": "vitest run --coverage",
    "start": "node --watch dist/index.js",
    "test": "vitest",
    "test:ui": "vitest --ui"
  },
  "type": "module"
```

Also, add that `"type": "module"` line to the end of the file. This will allow for consistent of ESM (`import`/`export`) syntax throughout the project, as opposed to the default of `commonjs` (`require`/`module.exports`).

To be clear, you `package.json` should be similar to this now:

```json
{
  "devDependencies": {
    "@tsconfig/node-lts": "^18.12.5",
    "@tsconfig/recommended": "^1.0.3",
    "@tsconfig/strictest": "^2.0.2",
    "@types/node": "^20.9.1",
    "@typescript-eslint/eslint-plugin": "^6.11.0",
    "@vitest/ui": "^0.34.6",
    "eslint": "^8.54.0",
    "eslint-config-prettier": "^9.0.0",
    "eslint-config-standard-with-typescript": "^40.0.0",
    "eslint-plugin-import": "^2.29.0",
    "eslint-plugin-n": "^16.3.1",
    "eslint-plugin-promise": "^6.1.1",
    "prettier": "3.1.0",
    "typescript": "^5.2.2",
    "vite": "^5.0.0",
    "vitest": "^0.34.6"
  },
  "scripts": {
    "build": "tsc --watch",
    "coverage": "vitest run --coverage",
    "start": "node --watch dist/index.js",
    "test": "vitest",
    "test:ui": "vitest --ui"
  },
  "type": "module"
}
```

---

Let's just make sure things are working now before committing our changes.

In `src/index.ts` place the following code:

```ts
export function add2Nums(a: number, b: number): number {
  return a + b;
}
```

In `src/index.test.ts` place the following code:

```ts
import { describe, expect, it } from "vitest";
import { add2Nums } from "./index.js";

describe("add2Nums", () => {
  it("should return the sum of two numbers", () => {
    expect(add2Nums(2, 3)).toBe(5);
    expect(add2Nums(-1, 5)).toBe(4);
    expect(add2Nums(0, 0)).toBe(0);
  });
});
```

[Curious about why we are importing from `./index.js`?](https://www.totaltypescript.com/relative-import-paths-need-explicit-file-extensions-in-ecmascript-imports)

Run: `npm t` and you should output similar to this:

```shell
 ✓ src/index.test.ts (1)
   ✓ add2Nums (1)
     ✓ should return the sum of two numbers

 Test Files  1 passed (1)
      Tests  1 passed (1)
   Start at  12:02:25
   Duration  242ms (transform 41ms, setup 0ms, collect 29ms, tests 3ms, environment 0ms, prepare 77ms)


 PASS  Waiting for file changes...
       press h to show help, press q to quit
```

You can press 'q' to quit the test runner. You can also run `npm run test:ui` to run the tests in the browser.

You can also do: `npm run coverage` to see a coverage report. Just follow the prompts as you will be prompted to install an additional package.

Coverage reports are kind of like a test report, but instead of showing you which tests passed and failed, it shows you which lines of code were executed and which were not. This is useful for finding dead code, or code that is not being used.

## Conclusion

In this lesson we updated our template repo to include Vitest. We also added a few scripts to our `package.json` to make running tests and coverage reports easier.
