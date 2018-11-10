# Build Modular Interfaces with Components

Learn how to quickly set up a React application with Create React App and separate your React components into modules.

## Understanding React Components (1:42)

- Just about everything in react is a component.
- Overview of the course

No Teacher's Notes

## Setting up with `create-react-app`

- used CDN links in privious course
- overview of how to use npx create-react-app
- npx makes it easy to install command line tools
- npx makes sure you are using the latest version of a package

Resources

- Create React App
- [Introducing npx: an npm package runner](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b)

## Using `create-react-app`

## Separating Function Componenets into Modules

## Separating Class Components into Modules

## Modules Review

# Managing State and Data Flow

It’s important to think carefully about where state resides in your application. In this stage, you will restructure state and data flow to be more unidirectional.

## Unidirectional Data Flow

## Lifting State Up

## Commmunicating Between Components

## Update State Based on a Player's Index

## Building the Statistics Component

## Controlled Components

## Adding Items to State

## Updating the Players State Based on Previous State

```JavaScript
handleAddPlayer = (name) => {
    this.setState( prevState => {
        return {
            players: [
                ...prevState.players,
                {
                    name,
                    score: 0,
                    id: this.prevPlayerId += 1
                }
            ]
        }
    })
}
```

Alternative using `concat() method:

```JavaScript
handleAddPlayer = (name) => {
  let newPlayer = {
    name,
    score: 0,
    id: this.prevPlayerId += 1
  };
  this.setState( prevState => ({
    players: prevState.players.concat(newPlayer)
  }));
}
```

## Managing State Review

Which of the following best describes unidirectional data flow?

# Stateful Components and Lifecycle Methods

This stage covers working with React component lifecycle methods. You will also learn to use conditional rendering to update your UI based on the current state.

## Designing the Stopwatch

- Oh shit!!

## Stopwatch State

## Update the Stopwatch State with componentDidMount()

## Resetting the Stopwatch

## Prevent Memory Leaks with componentWillUnmount()

## Review

# React Component Patters

Learn useful design patterns to use in your React components. These patterns will not only help prevent you from writing messy and over-complicated code, but also help you create flexible, more performant components that are easier to understand and maintain.

## Optimize Performance with PureComponent

## Destructuring Props

## Refs and the DOM

## Validate Props with PropTypes

## Static PropTypes and Default Props

## The React Challenge

## The React Challenge: Solution

## Review
