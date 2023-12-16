# Contacts Challenge Solutions

**⚠️ Warning: These are the solutions to the Contacts Challenge. Do not look at them until you have completed the challenge yourself!**

---

`edit.cy.js` (`PUT`)

```js
const FIRST_NAME_IN_FIXTURE = "Maria Fixture";
const CURRENT_EMAIL = "Maria.Fixture@hotmail.com";
const CURRENT_PHONE = "643-916-7554";
const EDITED_NAME = "Maria Edited";

it("edits a contact", () => {
  cy.intercept("GET", "/contacts", { fixture: "contacts.json" });
  cy.intercept("GET", "/contacts/*", { fixture: "contact.json" });
  cy.intercept("PUT", "/contacts/*", {
    statusCode: 200,
    body: {},
  }).as("updateContact");

  cy.visit("http://localhost:5173");
  cy.findByRole("link", { name: FIRST_NAME_IN_FIXTURE }).click();
  cy.findByRole("link", { name: /edit/i }).click();

  // Verify that the form loads with current information ℹ.
  cy.findByLabelText("Name").should("have.value", FIRST_NAME_IN_FIXTURE);
  cy.findByLabelText("Email").should("have.value", CURRENT_EMAIL);
  cy.findByLabelText("Phone Number").should("have.value", CURRENT_PHONE);

  // Update the name.
  cy.findByLabelText("Name").clear();
  cy.findByLabelText("Name").type(EDITED_NAME);

  cy.fixture("contacts").then((contacts) => {
    cy.intercept("GET", "/contacts", {
      statusCode: 200,
      body: contacts.map((contact) => {
        if (contact.name === FIRST_NAME_IN_FIXTURE) {
          return {
            ...contact,
            name: EDITED_NAME,
          };
        }
        return contact;
      }),
    });
  });

  cy.findByRole("button", { name: /save/i }).click();

  cy.wait("@updateContact").then(({ request }) => {
    const { name, email, tel } = request.body;

    // As long as our submissions is valid, we cna proceed with other assertions assuming that the GET intercept fired.
    expect(name).to.equal(EDITED_NAME);
    expect(email).to.equal(CURRENT_EMAIL);
    expect(tel).to.equal(CURRENT_PHONE);
  });

  cy.findByRole("link", { name: EDITED_NAME }).should("exist");
});
```
