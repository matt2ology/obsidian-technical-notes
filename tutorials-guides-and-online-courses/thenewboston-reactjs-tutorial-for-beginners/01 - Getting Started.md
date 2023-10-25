---
note-type: permanent
week-created: Week 42.2
date-created: 2023-10-17
long-form-date-created: Tuesday, October 17, 2023
time-created: 09:50 PM
source: https://www.youtube.com/watch?v=-AbaV3nrw6E&list=PL6gx4Cwl9DGBuKtLgPR_zWYnrwv-JllpA&index=1&ab_channel=thenewboston
---
# 01 - Getting Started

React is a JavaScript library for building user interfaces specifically: single page applications.

Whenever we write React, even though it's a JavaScript library, we won't be writing plain-old
JavaScript.

We will be using a flavor of JavaScript called `JSX`. This affords us features like allowing us to
write pure HTML within the file.

When run in the browser. It won't know `JSX` it only "understands" JavaScript.
To convert `JSX` to JavaScript we need to use a "transpiler".

In the tutorial [Bucky Roberts](../../authors-people-key-figures/thenewboston.md) says to include `<script src="browser.min.js></script>"`
so we can transpile our JSX files to basic JavaScript. As of 2017 [`babel-core/browser.min.js` is deprecated](https://github.com/fullstackreact/30-days-of-react/issues/17)

## Installation

### Current method as of (2023-10-17)

Today, as of 2023/10/17, React has been designed for gradual adoption from the start, and **you can use as little or as much React as you need**:

- Use [Online Playgrounds](https://reactjs.org/docs/getting-started.html#online-playgrounds) to get a taste of React.
- [Add React to a Website](https://reactjs.org/docs/add-react-to-a-website.html) as a `<script>` tag in one minute.
- [Create a New React App](https://reactjs.org/docs/create-a-new-react-app.html) if you're looking for a powerful JavaScript toolchain.

### The old way

At the time of the tutorial 2005/06/26 [Bucky Roberts](../../authors-people-key-figures/thenewboston.md) was using React version 15.1.0 where
both React and ReactDOM are available over a  [CDN](https://reactjs.org/docs/cdn-links.html). This is no longer recommended...
