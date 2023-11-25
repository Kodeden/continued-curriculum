# Starting to Use the TS Template Repo

Here's a link to the [GitHub Classroom assignment](https://classroom.github.com/a/k1mSs7ED). Clicking the link should create a new repo for you on your GitHub account. You'll want to clone that repo to your local machine. Don't forget about `npm install`!

This will be on ongoing repo that you will use for the next several lessons. You'll want to continually add to it and keep committing as we work through the lessons.

## Challenge #1

If you worked through the setup videos, then you have been exposed to using TS for basic functions. Time to test your skills!

Take this JS code and convert it to use TS.

```js
function greet(personName) {
  return "Hello, " + personName;
}
```

For now, `personName` can be a string. We'll get into more complex types later. Go ahead and paste that into your assignment repo in `src/index.ts`, replacing whatever is there.

![TS Errors Showing](./images/1-errors.png)

As soon as you paste that untyped code into JS, you'll see some errors. Solve them!

You'll want to remove the contents from `src/index.test.js` as the tests will be broken since we cleared out the previous code. Now, write new tests to prove that your code works.

---

**⚠️ DO NOT LOOK AT THE SOLUTION UNTIL YOU HAVE TRIED THIS YOURSELF!**

[Solution](./ts-1-solution.md)
