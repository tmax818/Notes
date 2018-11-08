# Introducing Props

## Setting and Using Props

At its simplest, React is a library for creating and updating HTML elements.

0:10
Our application so far is not that useful, it consists of a static user interface.

0:15
How would we customize the scoreboard, like add new players and modify scores?

0:20
In React, we use properties, or props,

0:22
to customize our components and pass dynamic information into them.

0:27
HTML elements accept attributes that give them further meaning and

0:32
additional behavior.

0:33
Attributes provide extra bits of information to the browser

0:37
like an element's ID, class name, or an image's alt text, for example.

0:41
Every React component and

0:42
element can receive a list of attributes just like HTML elements.

0:47
In React, this list is called properties, or props.

0:50
Props are a core concept in React, because it's how we get data into a component.

0:56
Most of the components in your UI will be configured with props.

0:59
For example, you'll add functionality to a component, have it behave a certain way,

1:04
and display its contents with props.

1:07
There are two main steps to using props in a component.

1:10
First, you write props in a component's JSX tag, using an attribute syntax.

1:16
Then the component needs to be able to take in that information and

1:20
use it in some way.

1:21
If you remember earlier, when we viewed the object representation of a DOM node

1:26
in a console, it had a built-in property named props.

1:29
And its value is an object containing the attributes passed to it and its children.

1:35
Every React element and

1:36
component has a props object containing the list of props given to it.

1:41
We can inspect the props of a element and a component in React DevTools.

1:45
So if you open up React DevTools and select the scoreboard container div,

1:51
over in the right pane you'll see the text Props.

1:55
The children prop shows that it's an array holding two objects.

2:01
And the className prop is the class given to the div, scoreboard.

2:07
Inspect the Header component, and

2:09
in the right pane you'll see that Props is an Empty object.

2:12
And that's right, because our Header component currently has no props.

2:17
Let's start by displaying the content of our Header component dynamically

2:21
using props.

2:22
In the header, we need to display two pieces of content, the title and

2:26
the total player count.

2:29
You pass props to a component via the component's JSX tag

2:33
at the place where it's used.

2:35
The Header tag is used in the App component, so

2:39
let's first add an attribute named title, and

2:43
set it to the string "Scoreboard".

2:47
You can give a prop any name you want, title is just a name that I made up.

2:51
But this could be named heading, banner, Title McTitleface, anything.

2:56
Next let's add a new prop named totalPlayers.

3:01
And it's good practice to use camel case for prop names consisting of two or

3:05
more words to make them more readable.

3:07
Now, the value for totalPlayers should be a number.

3:11
Anytime you pass a prop a value other than a string, like a number or a variable,

3:16
you should place it between curly braces so

3:18
that is gets evaluated as a JSX expression.

3:21
I'll pass totalPlayers a value 1, but you can pass it any number you'd like.

3:26
As you can see,

3:27
props look like custom HTML attributes that provide information to the tag.

3:33
If you open React DevTools and select the Header component, you should see the title

3:39
and totalPlayers props we passed to the Header tag here under Props.

3:44
So these two props are now available to be used in the Header component.

3:49
Next, we'll update our Header function to use these props.

3:54
When you define a component using a function,

3:57
the function gets one default argument from React,

4:01
a props object containing a list of props given to the component.

4:06
So let's enable the use of props in our Header component

4:09
by giving our function a parameter called props.

4:13
You can name this parameter anything you want, but

4:15
props is the name most commonly used.

4:17
So I recommend naming it props as well.

4:21
If I log props to the console

4:26
You'll see that props is an object with a key of title,

4:30
which has the value "Scoreboard" and a key of totalPlayers which has the value 1.

4:37
So now we want to place the values of these props into our

4:41
JSX inside the h1 and span, replacing the static text.

4:46
We'll need to access the title and

4:49
totalPlayers properties of the props object.

4:53
And you can do this with .notation.

4:54
Just as you'd access the property of any object literal in JavaScript, for

4:59
example, props.title and props.totalPlayers.

5:02
But you can't simply write props.title between the h1 tags.

5:10
As you can see, our page will literally display PROPS.TITLE.

5:15
Well, you learned that JSX accepts JavaScript expressions.

5:19
So we'll instead display the content using a JSX expression.

5:24
Again, a JSX expression is surrounded by curly braces.

5:28
So between the h1 tags, write props.title inside curly braces.

5:34
And let's replace just the number in the span after Players with curly braces.

5:42
And inside the curly braces, we'll write props.totalPlayers.

5:47
I'll give app.js a save.

5:49
And over in the browser we see that it works.

5:52
We see SCOREBOARD and PLAYERS: 1.

5:56
And you can change the value of the title and totalPlayers props here in

6:01
the Header tag, for example, My Scoreboard and 11 totalPlayers.

6:06
And we can see that the component updates the content.

6:13
Since JSX lets us write JavaScript expressions between curly braces,

6:19
we can do things like math operations, for example, props.totalPlayers + 1.

6:26
And we get two players.

6:28
We could write literal values like strings or

6:31
numbers, and concatenate strings, even call a function.

6:35
For instance, in the Header tag, I'll pass the totalPlayers prop

6:40
an arrow function that takes a number and adds 10 to it.

6:47
Now I can call this function inside the Header component

6:53
with props.totalPlayers, pass 5 as the argument.

6:59
And as you can see, it displays the value 15.

7:03
So remember, the JavaScript you write between the curly

7:07
braces needs to be an expression or something that returns a value.

7:12
I'll set totalPlayers back to 1 for now.

7:19
In the next step, you'll learn more tips and best practices for using props.

Resources

- [Components and Props](https://reactjs.org/docs/components-and-props.html)
