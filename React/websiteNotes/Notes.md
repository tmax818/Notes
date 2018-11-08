# Hello World

The smallest React example looks like this:

```JavaScript
ReactDOM.render(
 <h1>Hello, world!</h1>,
 document.getElementById('root')
);
```

[source](https://reactjs.org/docs/hello-world.html)

# Introducing JSX

```JavaScript
const element = <h1>Hello, world!</h1>;
```

This is JSX, a syntax extension to JavaScript. JSX produces React 'elements'.

## Why JSX?

- rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

- components are how [separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) works in React.

## Embedding Expressions in JSX

```JavaScript
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

You can put any valid [JavaScript expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions) inside curly braces in JSX.

```JavaScript
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

This code produces the following in HTML:

<div id="root">
<h1>Hello, Harper Perez!</h1>
</div>

"We split JSX over multiple lines for readability. While it isn’t required, when doing this, we also recommend wrapping it in parentheses to avoid the pitfalls of [automatic semicolon insertion](http://stackoverflow.com/q/2846283)."

I hope to someday know what the hell the above means!

## JSX is an Expression Too

"After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects."

"This means that you can use JSX inside of if statements and for loops, assign it to variables, accept it as arguments, and return it from functions:"

```JavaScript
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```

## Specifying Attributes with JSX

```JavaScript
const element = <div tabIndex="0"></div>;

const element = <img src={user.avatarUrl}></img>;
```

## Specifying Children with JSX

```JavaScript
const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);
```

## JSX Prevents Injection Attacks

## JSX Represents Objects

```JavaScript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

Is the same as:

```JavaScript
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

`React.createElement()` performs a few checks to help you write bug-free code but essentially it creates an object like this:

```JavaScript
// Note: this structure is simplified
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```

These objects are called 'React elements' they are a description of what you want on the screen

[source](https://reactjs.org/docs/introducing-jsx.html)

# Rendering elements

"An element describes what you want to see on the screen:"

```JavaScript
const element = <h1>Hello, world</h1>;
```

React elements are plain objects. React DOM updates the DOM to match React elements

## Rendering an Element into the DOM

this is a div in an HTML file:

```html
<div> id="root"></div>
```

everything inside this div is managed by React DOM.

"Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like."

```JavaScript
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

produces the following in HTML:

<div id="root">
<h1>Hello, world</h1>
</div>

## Updating the Rendered Element

React elements are [immutable](https://en.wikipedia.org/wiki/Immutable_object).

```JavaScript
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```

It calls `ReactDOM.render()` every second from a [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setInterval) callback.

[toLocaleTimeString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleTimeString) is a prototype method on the [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) object.

## React Only Updates What's Necessary

"React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state."

Check out the bottom of the webpage for this one!!!

[source](https://reactjs.org/docs/rendering-elements.html)

# Components and Props

"Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. This page provides an introduction to the idea of components. You can find a [detailed component API reference here](https://reactjs.org/docs/react-component.html)."

## Functions and Class components

This:

```JavaScript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

is the same as this:

```JavaScript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

from React's point of view.

## Rendering a Component

```JavaScript
const element = <Welcome name="Sara" />;
```

When React sees an element representing a user-defined component, it passes JSX attributes to this component as a single object. We call this object “props”.

For example, this code renders “Hello, Sara” on the page:

```JavaScript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

## Composing Components

```JavaScript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

## Extracting Components

"We recommend naming props from the component’s own point of view rather than the context in which it is being used."

What the fuck does this mean?

"A good rule of thumb is that if a part of your UI is used several times (Button, Panel, Avatar), or is complex enough on its own (App, FeedStory, Comment), it is a good candidate to be a reusable component."

## Props are Read-Only

"**All React components must act like pure functions with respect to their props.**"

[source](https://reactjs.org/docs/components-and-props.html)
