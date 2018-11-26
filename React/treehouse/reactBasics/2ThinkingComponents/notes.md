# Thinking in Components

## What is a Component?

- Everything in React is a component.

- overview of scoreboard app

Resources

- [Break The UI Into A Component Hierarchy](https://reactjs.org/docs/thinking-in-react.html#step-1-break-the-ui-into-a-component-hierarchy)

"a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

## Create a Component

React components are written in JavaScript.

### Header Component

```JavaScript
import React from 'react';

const Header = () => {
  return (
    <header>
      <h1>Score Board</h1>
      <span>Players: 1</span>
    </header>
  );
};

export default Header;
```

Resources

- [Functional and Class Components](https://reactjs.org/docs/components-and-props.html#functional-and-class-components)
- [Why use parenthesis on JavaScript return statements?](http://jamesknelson.com/javascript-return-parenthesis/)

## Use a Component with JSX

- capitals distinguish React components from HTML tags

* In React, your UI is a composition of functions

Resources

- [User-Defined Components Must Be Capitalized](https://reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized)

## Review

A **\_\_\_\_** renders a reusable piece of the UI.
How do you create a React component?
React uses a templating language for creating components. False

## Components as Arrow Functions

- converts Header component to arrow function syntax

Resources

- [Arrow functions – MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

Notes:

- [Introducing Arrow Function Syntax](https://teamtreehouse.com/library/introducing-arrow-function-syntax)

## Create the Player Component

- Starts with counter div in the Player component and leaves creating Counter component as an exercise.

```JavaScript
import React from 'react';
import Counter from './Counter';

const Player = () => {
  return (
    <div className="player">
      <span className="player-name">Tyler</span>
      <Counter />
    </div>
  );
};
export default Player;
```

Begins next video with solution below

```JavaScript
import React from 'react';

const Counter = () => {
  return (
    <div className="counter">
      <button className="counter-action decrement">-</button>
      <span className="counter-score">46</span>
      <button className="counter-action increment">+</button>
    </div>
  );
};

export default Counter;
```

No teacher's notes for this video

## Composing Components

- Composition - when one component contains another component

- adds app.js with classname "scoreboard"

- strike a ballance between too few components and too many granular components

### App.js

```JavaScript
import React, { Component } from 'react';
import Header from './Header';
import Player from './Player';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="scoreboard">
        <Header />
        <Player />
      </div>
    );
  }
}

export default App;
```

Resources

- [Composing Components](https://reactjs.org/docs/components-and-props.html#composing-components)
- [Extracting Components](https://reactjs.org/docs/components-and-props.html#extracting-components)
- [How do you know what should be its own component?](https://reactjs.org/docs/thinking-in-react.html#step-1-break-the-ui-into-a-component-hierarchy)

## React Developer Tools

Resources

- [React Developer Tools – Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)
- [React Developer Tools – Firefox](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)
- [react-devtools](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)
