# JSX

## Overview

`const element = <h1>Hello, Software Development World!</h1>`

This syntax is neither a string nor HTML.

It is called `JSX`, and it is a syntax extension to JavaScript. We recommend using it with React to describe what the UI should look like. `JSX` may remind you of a template language, but it comes with the full power of JavaScript.

`JSX` produces React “`element`s”. We will explore rendering them to the DOM in the next section. Below, you can find the basics of `JSX` necessary to get you started.

### Why JSX?

React embraces that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “`components`” that contain both. We will come back to components later, but if you’re not yet comfortable putting markup in JavaScript, this might convince you otherwise.

React doesn’t require using `JSX`, but most people find it helpful when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.

Let’s get started!

### Embedding Expressions in JSX

In the example below, we declare a variable called `name` and then use it inside JSX by wrapping it in curly braces:

```
const name = 'Vicki Bealman';
const element = <h1>Hello, {name}</h1>;
```

You can put any valid JavaScript expression inside the curly braces in JSX. For example, `2 + 2`, `user.firstName`, or `formatName(user)` are all valid JavaScript expressions.

In the example below, we embed the result of calling a JavaScript function, `formatName(user)`, into an `<h1>` element.

```
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Vicki',
  lastName: 'Bealman'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, {formatName(user)}</h1>);
```

[Try it here](https://codepen.io/drbealman/pen/poZgQKy)


We split JSX over multiple lines for readability. While it isn’t required, when doing this, we also recommend wrapping it in parentheses to avoid the pitfalls of automatic semicolon insertion.

