---
note-type: literature
date-created: 2023-11-17
long-form-date-created: Friday, November 17, 2023
week-created: Week 46.5
time-created: 06:08 PM
author: Jeff Delaney
---

# Test-Driven Development // Fun TDD Introduction with JavaScript

Related : [JavaScript](../4-hub-notes-🚉/JavaScript.md) - [Jest](Jest) - [Cypress](Cypress) - [Playwright](Playwright) - [Vite](Vite)

Source :

- [Fireship: Test-Driven Development // Fun TDD Introduction with JavaScript](https://www.youtube.com/watch?v=Jv2uxzhPFl4&ab_channel=Fireship)
- Previous video - [Fireship: Software Testing Explained in 100 Seconds](https://www.youtube.com/watch?v=u6QfIXgjwGQ&ab_channel=Fireship)

Topics : [Test Driven Development](Test%20Driven%20Development)

## Why Test?

Test Driven Development (TDD) is a technique that describes the behavior of code before
implementation

Writing tests walks the line of being valuable and a waste of time.

Testing:

- Reduce bugs
- Improve maintainability

Unit testing via Jest

End-to-end testing via Cypress

## Test-Driven Development (TDD) Philosophy

Automated testing is a way to write code that describes your requirements and
validates your main application code.

Typically, for a majority of programmers, don't write tests until the feature
is working. More often developers don't write tests at all; as a matter of fact,
this is especially true with front-end development because [User Interface](../4-hub-notes-🚉/User%20Interface.md)
requirements tends to change frequently.

Following the Test-Driven Development Philosophy: you'll write your test before
implementing code. The mantra is "red-green-refactor" which means you write a
failing test first (red), implement code to get it to pass (green), and then
you go back and optimize or refactor the implemented code.

It's not always practical, but when you have a project with very clear
requirements (i.e. a up-front design) writing code with a Test-Driven
Development style will improve your productivity.

## Functional Testing

Different testing strategies and see how they add value to a code base.

There are other terms that are used when talking about testing.

- [Acceptance testing](Acceptance%20Testing): test client or user's requirements
  (i.e. make sure the software meets assumptions and expectations)
- [System Testing](System%20Testing): Works on real hardware
  (i.e. does it work on the targeted computer/server/platform)
- [Sanity Testing](Sanity%20Testing)/[Smoke Tests](Smoke%20Tests): on large
  application you may have thousands of tests to run and may take a long time,
  delaying everyone else's work, so we prioritize the most important tests
  first to make sure the app is still functional before the rest of the test suite.

### Unit Testing (Short and Simple)

At the lowest level we have Unit-testing where the goal is to validate the
behavior of individual functions, methods, or just units of code.

### Integration Testing

Above unit testing we have integration testing: which involves testing multiple
units of code together; for example, you might have a react component and a
hook to fetch information from a database.

```jsx
function Feature() {
  const [data] = useDatabase("url");
  return <main>{data}</main>;
}
```

We can unit test each of these individually, but then have an integration test
to see how well they work together.

Like is the component actually able to use the hook to get the data that it
needs for the [User Interface](../4-hub-notes-🚉/User%20Interface.md).

### End-To-End Testing (Complex Integrations)

Runs your app in a simulated environment and attempts to emulate actual user
behavior.

[Jeff Delaney](Jeff%20Delaney) views end-to-end testing the most valuable in
his development.

#### Cypress

A browser-based test runner that allows you to program tests where user clicks
on buttons, fill out forms, and then asserts that the actual changes to the
[Document Object Model](Document%20Object%20Model) or the
[User Interface](../4-hub-notes-🚉/User%20Interface.md) are valid.

## Non-Functional Testing

Non-functional testing is to evaluate performance, usability, and security.
You'll hear terms like [Stress Testing](Stress%20Testing) or
[Failover Testing](Failover%20Testing) used to test the capabilities of the
infrastructure as opposed to the code itself.

## JS Interview Question

Implement a stack data structure where the last item in is the first item out.

## Setting up Jest

```bash
npm init vite
```

    Done. Now run:

      cd vite-project
      npm install
      npm run dev

```bash
npm install jest
```

will look for all files in project that end in `.test.js`

create a test directory

in `package.json` add the following under the `"scripts"` section

```json
"test": "jest --watchAll --verbose"
```

now run

```bash
npm run test
```

```bash
npm install @types/jest --save-dev
```

Then create a `jsconfig.json`

```json
{
  "typeAcquisition": {
    "include": ["jest"]
  }
}
```

This will allow VS code to provide IntelliSense for everything built into [Jest](Jest)

## Writing your First Test

Use the `describe` to describe the thing that I'm testing.

Ensure that our stack can be instantiated.

## Setup & Teardown

[Jest](Jest) has a set of helper for setup and tear down:

- `afterAll`
- `afterEach`
- `beforeAll`
- `beforeEach`
- `test`

Useful to reduce code duplication in a test suite.

### Example `beforeEach`

```js
describe("My Stack", () => {
  let stack; // Set a global variable for the stack

  // The beforeEach hook to re-initailize the stack before each new test
  beforeEach(() => {
    // Gives us an empty object to work with before each test
    stack = new Stack();
  });

  // Test Cases below...
});
```

## Code Coverage Report

Provides a high level, in percentages, of how well tests defined covers source code written

In the `package.json` file have `--coverage` appended to the Jest command

```json
"test": "jest --watchAll --verbose --coverage"
```

## Cypress E2E

Cypress uses a jQuery like syntax that allows one to match a DOM element to do various
actions and inputs along with their corresponding expectations.

Unlike a unit test which is designed to be fast and simple an end-to-end
is very long and complex, and takes a while to run.

It simulates actual user behavior in the browser.

We could use [Jest](Jest) with the puppeteer package; however, Cypress provides
a realistic environment by leveraging a real browser to simulate and execute defined
actions a user may do.

[thenewboston](../authors-people-key-figures/thenewboston.md) pairs Cypress with the firebase emulator to create
a mock database and mock user authentication. Doing so allows him to test
his apps efficiently in an environment that looks very similar to how they look
in production environment that looks very similar to how they look
in production.

### Installing Cypress

```sh
npm install cypress -D
```

In the `package.json` file we can add an end-to-end script that runs the
cypress open command

```json
"e2e": "cypress open"
```

This opens the test-runner and comes with a bunch of built-in examples.

Back in source code a Cypress directory will be created. The source code for the
example test is kept in the `cypress\integration\example\actions.spec.js`.

Like in [Jest](Jest) a test suite is defined then inside multiple tests are described with
the `it` keyword.
