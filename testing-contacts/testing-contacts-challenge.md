# Testing ✅ the KodeDen 'Final Project' 🏁 for the Contacts 📖 Challenge

## Review of Testing ✅ Concepts

I'll be sharing some of the tests ✅ that I have used in the aforementioned challenge. It may be more meaningful if you have already completed the challenge and attempted the testing portion, but it's 🆗 if you haven't yet. Just be sure to go back to it! You will be getting some potential spoilers with regards to some suggested tests for the app, but no actual app code will be revealed.

These lesson is meant to be more of a thorough review. The assumption is that you have already picked up on testing ✅ concepts in our previous lessons (on EduFlow) and/or through our interactive Q&A sessions. If you haven't, then you should go back and review those lessons and/or ask questions in our Q&A sessions.

### What is Testing ✅?

Testing ✅ is the process of checking that your code does what you expect it to do. It is a way of ensuring that your code is correct, and that it will continue to be correct as you make changes to it. That last part is important, because as you add more features to your code, you don't want to break the existing features and you certainly don't want to have to open a browser and constantly manually click through things over and over again. This is the main motivation for **automated testing ✅**.

### What is a Test ✅?

A test ✅ is a piece of code that checks that another piece of code does what it is supposed to do. A test ✅ is usually written by the same person who wrote the code that it is testing ✅, but it can also be written by someone else. A test ✅ is usually written in the same programming language as the code that it is testing ✅, but it can also be written in a different language. A test ✅ is usually run automatically by a computer (e.g. '⌚ mode'), but it can also be run manually by a human.

These tests are most paramount as we start adding new features ✨ to our code and/or refactor ♻️ our code. We want to make sure that we don't break anything that was already working. This is where automated testing ✅ comes in. We can write tests ✅ that check that our code does what it is supposed to do, and then we can run those tests ✅ automatically every time we make a change to our code. This way, we can be sure that we haven't broken anything. This is a normal part of a **continuous integration** (CI) process.

### What is a Testing Framework?

For JS, the most common testing framework is Jest, but we use Vitest which is a faster ⚡, drop-in replacement for Jest.

We mentioned Jest and Vitest, but for what? A testing framework is a set of tools that help you write tests ✅. It provides a way to write tests ✅, a way to run tests ✅, and a way to see the results of tests ✅. It also provides a way to organize your tests ✅ into groups, and a way to run only some of your tests ✅ at a time.

Moreover, it's a collection of commonly used functions that mirror the terminology we use with testing. Mainly: `describe`, `it` (or `test`), `expect` and various iterations of `toBe` to name a few. There are also ways to mock 🤡 things like ⏲️ timers. After all, we can't sit around and actually wait for a timer to run its course every time we want to test!

### Testing Strategies and Types of Tests ✅

#### Static Analysis Testing (Linting)

These are tests that check your code without actually 🏃🏾‍♂️ it, AKA **linting.** The tooling that we have set up in our template repositories is already doing this for you and generating errors 🥅 and ⚠️s for you right there in VS Code. Generally, these tools are following pre-determined style guides and are on the lookout for things like unused variables, syntax errors 🥅, and even things that appear to violate established best practices. These types of tools can be configured to a team's specifications to be as strict or loose as they want. Our set up is quite strict, of course 😈.

To supplement linting, we have Prettier that takes care of consistent formatting of our code. However, that is purely stylistic and would not be considered a test ✅.

#### 😶‍🌫️ Smoke/Snapshot Tests

These typically just check that an app starts up without crashing. The name is a reference to powering on some electronic equipment, where we hope 🤞🏾 that it doesn't start 🚬❗

In the case of React, we want to know whether or not a component successfully renders. More specifically, these are snapshot tests.

We render our app and, upon success we capture a snapshot of the rendered DOM nodes. Later, if we do an update on our component(s), our testings will fail and we can see the difference between the old and new snapshots. In this case, a failure is not a bad thing, we just have to update our snapshots. These tests don't necessarily provide much overall value, and some teams don't bother with them. They are simple enough to create, and we have sprinkled a few in previous lessons.

#### 🧪 Unit Tests

These are the most commonly written tests in programming in general. Here, we are testing individual units of our code (a la functions). These tests isolate a single function and check that it does what it is supposed to do.

```js
it("should alphabetize contacts by last name first and then first name (if applicable)", () => {
  // Arrange
  const contacts = [
    { name: "Alice Johnson" },

    // 'Bob Smith' starts off in front of 'Alice Smith' 👇🏾
    { name: "Bob Smith" },
    { name: "Charlie Brown" },
    { name: "Alice Smith" },
    { name: "Diana Ross" },
  ];

  const expectedResult = [
    { name: "Charlie Brown" },
    { name: "Alice Johnson" },
    { name: "Diana Ross" },
    { name: "Alice Smith" },
    { name: "Bob Smith" },
  ];

  // Act
  const result = alphabetizeContactsByLastName(contacts);

  // Assert
  expect(result).toEqual(expectedResult);
});
```

The general format of these tests follows the 3️⃣ As: Arrange, Act, Assert. We arrange the data that we need for our test ✅, we act on the code that we are testing ✅, and then we assert that the result is what we expect it to be. Notice that this has been labeled in the example code above ☝️.

##### What About Function Components?

This is where the terminology overlaps a bit. We could call 🏃🏾‍♂️ and rendering a function component as a 😶‍🌫️ smoke/snapshot test, or we could call it as a unit test as it's a single function. However, given that React components lend themselves to being integrated into other functions and managing interactions and state, we will be treating them as integration/interaction tests.

### 🤝 Integration/Interaction Tests

These are the most commonly written tests ✅ as per the creator [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/), Mr. Kent C. Dodds:

> Write tests. Not too many. Mostly integration.

React Testing Library is actually a subset of Testing Library. If you haven't already, you should [review the philosophies and principles of Testing Library](https://testing-library.com/docs/) as a whole. Summarily

> (Testing Library) is a light-weight solution for testing web pages by querying and interacting with DOM nodes (whether simulated with JSDOM/Jest or in the browser). The main utilities it provides involve querying the DOM for nodes in a way that's similar to how the user finds elements on the page.

---

> The more your tests resemble the way your software is used, the more confidence they can give you.

---

In other words, it is meant to test ✅ the DOM as a user would interact with it. This is in contrast to the more traditional approach of testing ✅ the DOM as a developer would interact with it. This is a subtle but important distinction. We are not testing ✅ the implementation details of our code, but rather the user experience of our code. In this regard, testing UIs in the DOM built with React or whatever differs from traditional unit testing of functions.

Testing Library, and hence React Testing Library, places a high emphasis on accessibility ♿. The aforementioned queries prioritize accessibility and semantics, [prescribing a specific priority order](https://testing-library.com/docs/queries/about/#priority) of performing said queries.

```js
describe("Navigate to a contact and back", () => {
  it("navigates to the first contact", async () => {
    // We will click the first contact
    const expectedHeading = data.contacts[0].name;
    const expectedPhone = data.contacts[0].tel;
    const expectedEmail = data.contacts[0].email;
    const { user } = setup(<App />);

    const firstContact = screen.queryByText(data.contacts[0].name);

    await user.click(firstContact);

    await screen.findByText(expectedPhone);

    const heading = screen.getByRole("heading", { name: expectedHeading });

    expect(heading).toBeInTheDocument();
    expect(screen.getByText(expectedEmail)).toBeInTheDocument();
  });

  it("navigates back to the list of contacts whenever a user clicks the 'back' button", async () => {
    const { user } = setup(<App />);

    const firstContact = screen.queryByText(data.contacts[0].name);

    await user.click(firstContact);

    await screen.findByText(data.contacts[0].tel);
    const backButton = screen.getByText("⬅️ Back");

    await user.click(backButton);

    const contacts = await screen.findAllByRole("listitem");
    expect(contacts).toHaveLength(data.contacts.length);
  });
});

describe.skip("Search for a contact", () => {
  it("displays the contacts that match the search term", async () => {
    const user = userEvent.setup();

    render(<App />);

    const searchTerm = "j";
    const expectedContacts = data.contacts.filter((contact) =>
      contact.name.toLowerCase().includes(searchTerm),
    );

    const searchInput = screen.getByLabelText(/Search/i);
    await user.type(searchInput, searchTerm);

    const contacts = await screen.findAllByRole("listitem");
    expect(contacts).toHaveLength(expectedContacts.length);
  });
});

/**
 * In Vitest (and presumably Jest) we can mark some tests as 'skipped' so that they are not run.
 * This is useful for tests that are not yet implemented, or tests that are failing and we want to focus on other tests first.
 */
describe.skip("Add a new contact", () => {
  it("displays the form to add a new contact", async () => {
    const { user } = setup(<App />);

    await user.click(screen.getByRole("link", { name: "Add Contact" }));

    expect(await screen.findByLabelText(/Name/i)).toBeInTheDocument();
  });

  it("adds the new contact to the list of contacts", async () => {
    const { user } = setup(<App />);

    await user.click(screen.getByRole("link", { name: "Add Contact" }));

    const nameInput = screen.getByLabelText(/Name/i);
    const phoneInput = screen.getByLabelText(/Phone/i);
    const emailInput = screen.getByLabelText(/Email/i);
    const submitButton = screen.getByRole("button", { name: "Save" });

    const name = "John New Contact";
    const phone = "123-456-7890";
    const email = "john@email.com";

    await user.type(nameInput, name);
    await user.type(phoneInput, phone);
    await user.type(emailInput, email);

    await user.click(submitButton);

    expect(await screen.findByText(name)).toBeInTheDocument();
  });
});
```

In the tests above, we see this line: `const { user } = setup(<App />);`. This is a custom function that we have created to help us with our tests. It is a wrapper around the `render` function from React Testing Library. It returns the `render` function's return value, but also returns a `user` object that we can use to interact with the DOM. This is a common pattern in testing ✅ React apps. It's usually set up in a file called something like: `setup-tests.js` or similar. This file is then noted in our `vite.config.js` file so that it gets referenced by Vitest.

```js
import "@testing-library/jest-dom";
import { cleanup, render } from "@testing-library/react";
import userEvent from "@testing-library/user-event";
import { afterEach } from "vitest";

/**
 * It is critical to always clean up the DOM and 'reset' the testing environment AFTER EACH test.
 * This is what the 'cleanup' function does.
 *
 * In this way, we can be sure that each test is starting with a clean slate.
 *
 * It's similar to  🏃🏾‍♂️ experiments in a lab 🥼.
 * You don't want to start a new experiment with the remnants of the previous experiment still in the lab,
 * possibly contaminating your results.
 */
afterEach(() => {
  cleanup();
});

// This takes in our function component that we want to test.
export function setup(jsx) {
  return {
    user:
      /**
       * In modern React Testing Library, we use the 'userEvent' library to simulate user interactions, not `fireEvent`.
       * There are a few exceptions though.
       *
       * As always, consult the docs 📝 and/or ChatGPT.
       */
      userEvent.setup(
        // Make sure that this doesn't break any other tests in the suite.
        { delay: null },
      ),

    // Think of this like a 'mix-in' of the entries from the returned object.
    ...render(jsx),
  };
}
```

#### Mocking 🤡

In this test: `it("adds the new contact to the list of contacts", async () => {`, we are directly interacting with our database. The same is true here: `it("navigates back to the list of contacts whenever a user clicks the 'back' button", async () => {`. We see references to `data`, which comes from the following: `import data from "../../db.json";`. Granted, this is a 'fake' JSON database, but it is still a database.

Direct interactions with a database, although not as egregious when using `json-server`, are not ideal for a few reasons:

1. We are not testing ✅ our app in isolation, we are testing ✅ our app and our database. Our tests might fail intermittently due to external database issues.
1. A real database is always changing. We can't realistically import it and then just compare `length`s, etc. 👎🏾
1. We pollute the database with test data, in the case of adding contacts.

To get around this, we can mock 🤡 our database. This is a common practice in testing ✅. We can create a fake database that we can use in our tests. This fake database will behave like a real database, but it will not actually store any data. It will just store the data in memory, and it will be reset every time we run our tests. This way, we can test ✅ our app in isolation, and we don't have to worry about polluting our real database with test data.

1️⃣ common way to manage this in the JS ecosystem with React Testing Library is to Mock Service Worker(`msw`). It's even mentioned in [the React Testing Library docs 📝.](https://testing-library.com/docs/react-testing-library/example-intro/#mock)

In a nutshell, `msw` will intercept our requests, preventing them from touching the database server or the API. Instead, it will return a fake response that we can control. This way, we can test ✅ our app in isolation, and we don't have to worry about polluting our real database with test data.

For a more in-depth at using `msw` with React Testing Library, check out [this lesson](./msw.md).

### 🧪 End-to-End (E2E) Tests

This is where tools like [Cypress](https://www.cypress.io/) and [Playwright](https://playwright.dev/) come in. These are tools that allow us to write tests that interact with our app in a browser. They are similar to integration/interaction tests, but they are more focused on the user experience. They are also more focused on the end-to-end flow of our app, rather than individual units of our code.

Generally, these are a bit more enjoyable and simpler to write than traditional tests with React Testing Library. It's arguable that they don't emphasize accessibility ♿ as much as React Testing Library, but they are still very useful. And, besides, linting configurations can help us with accessibility ♿ issues.
