# Understanding state

## What is State (4:15)

There are two ways that data gets handle than react, props and state. So far we built our application using functions that taken props and return react elements. But props are read-only or immutable. A component can only read the props given to it, never change them. For any data that's going to change, we have to use state. Let's dig into this concept.

In react, **state is the data you want to track in your app**. State is what allows you to create components that are dynamic and interactive, and it's the only data that changes over time. In react, this data is stored in state.

**State itself is a regular JavaScript object with properties that define the pieces of data that change**. For example, if I look at the final app in React Dev Tools and select the app component, we see this new section in the right panel labeled state, and it contains an array with three objects. If I expand one of the objects we see its properties, id, name, and score. This should look familiar.

Now the biggest difference between the players array, we're currently passing to app via props and this array and state, is that data in state is not read-only. This data can change. For example, if I click to remove a player, notice how the array changes from 3 to 2 objects. This triggers a State change that affects all the components that take in this data. For instance, the total players number changes to 2 and the total points decrease. And if I click to increase one of the player score, we see the score update in state as well. And we know that this state is also being shared with the stats component up top because we see the total points increase and decrease as we update the score.

In fact, I can even update the score here in the state object and watch the value immediately change on screen. I'll do the same with one of the names, and so on. So as you can see, **state is what keeps your UI in sync with your data**. As the data changes, different components of the app will update what they show to the user. And normally, in a regular JavaScript application, the more data you have and the more spread out it is the more complex the application becomes to maintain and debug. So react provides a more convenient way to store and maintain your data with state.

Props still play a major role in your application, data from state is distributed through props. For example, each player component still receives the name, score, and other information you'll learn about later from props. Props are still how you get data into a component. You can learn more about what defines state in the teachers notes. To begin using state, we need to make a few changes in our app. State is only available to components that are class components. So in the next video, 4:10 we´ll begin by converting a function component to a class component.

Resources

- [Adding Local State to a Class – React docs](https://reactjs.org/docs/state-and-lifecycle.html#adding-local-state-to-a-class)
- [Component State – React docs](https://reactjs.org/docs/faq-state.html)
- [props vs state](https://github.com/uberVU/react-guide/blob/master/props-vs-state.md)

## Create a Component as a Class (4:00)

## Create a Stateful Component (4:21)

## Handling Events (2:56)

## Updating State (2:14)
