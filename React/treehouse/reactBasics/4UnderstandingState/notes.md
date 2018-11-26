# Understanding State

## What is State?

State is the data you want to track in your app. It is the only data that changes over time.

"State itself is a regular JavaScript object with properties that define the pieces of data that change."

State is a POJO!

Resources

- Adding Local State to a Class – React docs
- Component State – React docs
- props vs state

## Create a Component as a Class

## Create a Stateful Component

"You can think of the render method in a class component as being a function of not just props, but props and state. In other words, if either props or state changes, React executes the render method to update what gets displayed to the user."

```JavaScript
import React from "react";

class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0
    };
  }

  render() {
    return (
      <div className="counter">
        <button className="counter-action decrement">-</button>
        <span className="counter-score">{this.state.score}</span>
        <button className="counter-action increment">+</button>
      </div>
    );
  }
}

export default Counter;
```

or class property syntax

```JavaScript
import React from "react";

class Counter extends React.Component {

  state = {
      counter: 0
    };
  }

  render() {
    ...
```

Resources

- constructor – MDN
- super – MDN
- Adding Local State to a Class
- Babel’s Transform Class Properties Plugin: How it Works and What it Means for your React Apps
- Is it better to define state in constructor or using property initializers?
  Related content
- Working with Classes in JavaScript
- Adding Properties Inside the Constructor Method

## Handling Events

Resources

- Handling Events – React docs
- [Passing Arguments to Event Handlers](https://reactjs.org/docs/handling-events.html#passing-arguments-to-event-handlers)

Notes:

There is a lot here and this is what's fucking me.

- [Supported Events in React](https://reactjs.org/docs/events.html#supported-events)

## Updating State

- state is never modified directly;
- "You pass setState, an object that contains the part of the state you wanna update, and the value you want to update it to."

Resources
[setState()](https://reactjs.org/docs/react-component.html#setstate)
[Using State Correctly](https://reactjs.org/docs/state-and-lifecycle.html#using-state-correctly)
[Understanding React setState](https://css-tricks.com/understanding-react-setstate/)

## Bind Events Handlers to Components

"In objects or classes, _this_ usually refers to the parent that owns the method."

"The other common way to bind event handlers is with an arrow function."

"arrow functions use what's called a 'lexical this binding' which means that it automatically bind them to the scope in which they are defined."

Resources

- [Handling Events – React docs](https://reactjs.org/docs/handling-events.html)
- [Passing Functions to Components](https://reactjs.org/docs/faq-functions.html)
- [This is why we need to bind event handlers in Class Components in React](https://medium.freecodecamp.org/this-is-why-we-need-to-bind-event-handlers-in-class-components-in-react-f7ea1a6f93eb)
- [React — to Bind or Not to Bind](https://medium.com/shoutem/react-to-bind-or-not-to-bind-7bf58327e22a)

Another way to bind an event handler is in the class constructor:

```JavaScript
constructor() {
  super();
  this.state = { score: 0 };
  this.incrementScore = this.incrementScore.bind(this);
}
```

Then pass the function to a React event like so:

```JavaScript
<button onClick={ this.incrementScore }> + </button>
```

## State and Events Review

What type of components allow you to initialize state?
The only required method in a class component is:
Can you define any stateless functional component as a class?

## Update State Based on Previous State

"So because state maybe updated asynchronously, whenever you need to update state based on previous state, you shouldn't rely on `this.state` to calculate the next state."

```JavaScript

...
incrementScore = () => {
  this.setState( prevState => {
    return {
      score: prevState.score + 1
    };
  });
}

```

Resources

- [setState()]()
- [State Updates May Be Asynchronous](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-may-be-asynchronous)
- [State Updates are Merged](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-are-merged)
- [Why doesn’t React update this.state synchronously?](https://reactjs.org/docs/faq-state.html#why-doesnt-react-update-thisstate-synchronously)

## Create the Application State

## Remove Items From State

## Understanding State Review
