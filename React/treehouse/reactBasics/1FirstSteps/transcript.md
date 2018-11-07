# First Steps in React

## Introducing React

React, a JavaScript library for building user interfaces. React introduces a more efficient and flexible way of building, organizing and maintaining your UI code.

One of the main benefits of working with React, is that it lets you build your application's user interface by breaking it up into small reusable pieces of code called **components**.

For example, let's say that you're building a book review app using only HTML and JavaScript. You'll most likely create the UI by combining elements like `divs`, `spans`, `inputs` and others. There are sections or pieces of the UI that you will likely reuse over and over again.

For instance, there might be a star rating widget and a comments area for each book review. While those sections are composed with HTML elements like `divs`, headings, paragraphs and images, each section can be thought of as a self-contained component.

React provide tools for us to create our own custom components, then quickly compose or combine them together to build complex interactive UIs. This means we can design, build, even test a component once and then reuse it as needed in our application. The other big benefit is that React keeps your application's data or state and the UI in-sync and can efficiently update you UI when data changes. This is one of the most difficult parts of building interactive user interfaces. When building UIs with JavaScript, we often have some sort of data model. For example, we might use arrays and objects to describe our data.

In the book review app for instance, reviews might be represented as an array of objects, with each object being one book reviewed. Imagine maintaining an application with hundreds or thousands of reviews. The programming or bookkeeping needed to manually keep visual elements like comments and ratings for all reviews in-sync with their JavaScript data model, can quickly go out of control, especially as you add more and more features.

So React includes clever features that remove much of the complexity around building your UI and keeping it in-sync with your application data. Allowing you to focus more on what your application should look like at any given moment, instead of how to change it over time. You're gonna learn more about components, applications state, organizing and managing your UI code and other core features of React, as you progress through this course, building your first react app.

Resources

- [reactjs.org](https://reactjs.org/)
- [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

## Add React to a Project

There are a few ways you can install and use React. You can read about the most common ways when you visit React's documentation at [reactjs.org](reactjs.org), and click Docs. You'll find that the React Docs are helpful and easy to read, and I encourage you to refer to them frequently, and keep them handy when building your React projects.

### Create React App

So as listed here in the docs, two common ways to install and get set up with react is with a tool called Create React App. And it's CDN or content delivery network links. Create React App was built by developers at Facebook to help save you from the time consuming setup and configuration that building a react application normally requires. There can be a lot of moving parts, from third party libraries to install, lots of configuration, build tools, and other tasks. Create React App is the most common way to get up and running quickly with React. It automatically sets up a build system, and creates the files and folders you need to get started with React. Now, using the tool does require that you have Node and NPM installed on your computer, and that you're a little bit familiar with the command line.

But you're not gonna have to install anything in this course, because we're going to add React to our project using the CDN links. This means that the React library is hosted by a third party service which we can link to in our project using the provided URLs. That way you can initially focus on just the ins and outs of React. But don't worry, you'll learn how to use React with build tools and create React app in a later course.

To code along with me, you can download the project files for this course and open them in your preferred text editor. Or launch the workspace with this video. I am going to use Visual Studio Code and to get it started, I have prepared the three main files that we are going to use, index.html, app.css and app.js. app.css contains the styles for our project. Now, we won't be working with the CSS as we go through the project but feel free to change it as you please. In the file index.html, you'll notice that I've included React in our project using these script tags and the React CDN development links provided in the docs.

Now, when building web applications in React, you use two libraries, react and react-dom. So why two separate libraries and what's the difference? Well, you see React started out as a library for building interfaces in the browser. The patterns and tools it provides are so useful that React has been extended to native application development with React Native. That means React can run on phones, tablets, even TVs and game consoles. So when React Native came along, react and React-dom were split into two libraries.

Now, you're going to learn how to build with React in the browser. So first, it's linking to the core React library. And react-dom is the library for building web apps and is what lets React connect to and manipulate the dom. Now, below the CDN links, I included a script tag that links to the file app.js. And this is where we will be writing our code. All right, now that our project has access to React, we'll get into coding in the next video.

Now, if you're using a text editor like Visual Studio Code or Atom, I suggest that you install the Babel JavaScript extension or package for your text editor. It's gonna provide helpful syntax highlighting for a lot of the code that we're going to write. In addition, you'll need to run your React project on a local development server. I've posted information about setting up a local development server, as well as links to Babel extensions and packages for text editors in the teacher's notes with this video.

## Creat A React Element (4:37)

Earlier I mentioned that one of the benefits of using React is that it's component based. You create your UI as individual self contained components. But we're not going to start off by writing components. You see, at its core, React is only a library for creating and updating HTML elements in your UI, that's all it does. So to better understand how React creates UI, we're going to begin using the React API to create React elements. Which are the smallest building blocks of React apps. Once you have a basic understanding of how React describes and creates elements in your UI, it will be a smoother transition into understanding components and writing JSX. The special syntax React uses to create elements and use components.

React provides the `createElement` function to create and return elements. In app.js, the first thing we'll do is create a new variable named title, then we'll call React.createElement.

```JavaScript
const title = React.createElement(
  'h1', //
  {id: 'main-title', title: 'This is a title'},
  'My First React Element!'
  )
```

createElement accepts three arguments that define the element you want to create.

1.  The first argument is the type of element you want to create. This is usually a string which represents an HTML element or a tag. In this case, I want to create an h1 element so I'll pass it the string h1, but this could also be div, span, p, and so on. And for readability I'm placing each argument on a separate line.
2.  The second argument you pass to React.createElement is an object containing any attribute and value you want to give the element. For example to give the h1 element in id we can later target with CSS, I'll pass an object and inside it write an id property and set it to main-title. You can add as many comma-separated properties as you want to this object. For instance, I'll add a title attribute with title and set it to, this is a title. Now, if we're not giving the element any attributes, you can pass it an empty object, or the value null.
3.  The third argument you pass to React.createElement, is the content or children of the element you're creating. For instance any text that will display between the opening and closing h1 tags. It could also be more elements created by `React.createElement` or it could even be null. I'll pass in the string, 'My First React Element.'

React does not create actual DOM nodes. It's not creating in the way you would expect. For instance the title element we defined is not a real h1 element. It's actually an object that describes a DOM node. **It's an object representation of a DOM node.** To better demonstrate, I'll console.log(title) to see what output we get. Over in the browser console we see the title react.element recreated, represented as an object. It has several properties like key, props, and ref. Now the important one is to pay attention to right now our type and props. Notice how the value for type is h1, the value for props is an object containing the id and title properties we passed to createElement, and the value for children is the string, 'My First React Element', which we passed as the third argument.

So, this React element is an object describing what you want to render to the DOM, or Display on the Screen. For example, when the h1 get's rendered to the DOM, we should have a html element that looks like this. The type property, describes what type of element we want to create in h1 element. Props are like the properties or attributes of that element in this case it will have a title and id attributes. And the children property string value will be turned into a text node that reads, 'My First React Element.' So this concept is the essence of React. The elements that React creates are actually plain JavaScript objects that describe the element you'd like to display to your UI. So how does React render a real DOM node? You'll learn about that next.

Resources

- [createElement()](https://reactjs.org/docs/react-api.html#createelement)

## Render an Element (6:18)

0:00 You learned that React does not create real DOM nodes. 0:04 By DOM nodes, I mean an actual h1, div, span, or a text node. 0:08 Instead, React creates plain JavaScript objects that describe DOM nodes. 0:13 For example, in the previous video, we used React.createElement 0:19 to create a React element that describes an h1 with an id and 0:23 title attribute and text as its children. 0:27 So how does this object representation of a DOM node get rendered and 0:32 displayed on the page?

```JavaScript
const title = React.createElement(
  'h1', //
  {id: 'main-title', title: 'This is a title'},
  'My First React Element!'
  );

  ReactDOM.render(
    title,
    document.getElementById('root')
    );
```

0:33 Well, the ReactDOM library, 0:35 included in our project, provides DOM specific methods. 0:39 The one you'll use the most is `ReactDOM.render()`, 0:42 which renders React elements to the DOM. 0:45 Back in app.js below the title variable, 0:50 let's call ReactDOM.render. 0:54 So this is the function that actually does the creating and updating of the DOM. 0:59 It's what connects React to the DOM. 1:01 Render accepts two arguments. 1:04 The React element or JavaScript object that describes the element you'd like to 1:09 render and the actual HTML element you want to update or render to.

1:15 So to render the title React element to the page, 1:18 let's pass title as the first argument. 1:22 And as the second argument, we'll use the plain JavaScript 1:27 document.getElementById method to target a DOM element with the id root. 1:33 So this is the container element where our code will be rendered by React and 1:38 there is no significance in the id root. 1:41 You'll often see it named app or container, 1:43 you can name it anything you want. 1:46 Next, we'll need to create this root element in our HTML file. 1:51 Open index.html and 1:54 create a div just below the opening body tag and above our scripts. 2:00 Add an id and set it to root. 2:04 And that's really all the work we'll need to do in index.html. 2:08 The React code we write in app.js will be rendered into this root div. 2:15 Or in React terms, this is where we will be mounting our React application.

2:20 Over in the browser when I refresh, 2:23 we see the heading displaying the text on the page. 2:26 And if we inspect the DOM with Chrome dev tools, we see the h1 element with 2:31 the id and title attributes we described with createElement. 2:40 Any existing DOM elements inside the root div will be replaced 2:45 when render is first called. 2:47 So for example, if I add the text Loading inside the div when I refreshed 2:52 the browser, you'll see the text get immediately replaced with the h1. 2:58 So everything inside the root DOM element gets managed by ReactDOM.render.

3:04 Now applications usually consist of more than just a heading. 3:09 So let's create other elements and compose them together. 3:12 I'll create a description element and a header that wraps both the title and 3:17 description. 3:18 So just below the title variable, I'll create a new variable that named desc or 3:25 description, Assign it React.createElement. 3:32 And I wanna create a paragraph so I'll pass the string p as the type argument. 3:37 I'm not gonna assign this element any properties, so 3:41 I'll pass it null as the second argument. 3:44 And as the third or children argument, 3:48 I'll pass it the string I just learned how to 3:53 create a React node and render it into the DOM. 4:03 You can provide the children as any number of arguments after the props argument. 4:10 createElement considers anything after the second argument as children.

4:15 Next, I'll create a header element by declaring a variable 4:21 named header and assigning it React.createElement. 4:29 I want to describe a header element here so 4:33 I'll pass it to string header as the first argument. 4:37 I will pass it null as the second argument since I don't wanna sign 4:41 the header any properties. 4:44 Now this header is going to contain the title and 4:47 description elements we just created. 4:50 So I'll pass it the title and desc variables as the children. 4:57 Finally, let's render the parent header by 5:01 passing the header variable to ReactDOM.render. 5:06 I'll give app.js a save, and over in the browser when I refresh, great. 5:12 We see a header element with child h1 and p elements.

5:19 So the main takeaway here is that React never touches the actual DOM directly. 5:25 It just manages what gets rendered to the DOM and 5:28 what gets updated via reactDOM.render. 5:31 It's not until render that the browser creates actual DOM elements 5:36 like our header and its children. 5:38 So in other words, it's renders job to interpret the element objects and 5:43 create DOM nodes out of them.

5:49 At this point you might be thinking, wow, it took three function calls and 5:53 way too many lines of code just to create three elements. 5:56 How exactly does React make it easier to build and maintain my UI? 6:00 And you're probably right. 6:01 React.createElement doesn't seem all that convenient right now. 6:05 It makes it tricky to visualize the elements you're creating. 6:09 But don't worry, React uses a faster, easier, and 6:12 friendlier way to create elements with a special syntax called JSX. 6:16 You'll learn about it in the next video.

Resources

- [ReactDOM](https://reactjs.org/docs/react-dom.html)
- [render()](https://reactjs.org/docs/react-dom.html#render)

## Introduction to React Review(6 questions)

1.  Which of the following best describes React?

1.  A JavaScript library for building user interfaces
1.  A full-fledged JavaScript framework
1.  A set of jQuery plugins for building reactive websites
1.  A JavaScript animation framework

1)  Which library lets React connect to and update the DOM?

1)  Webpack
1)  Babel
1)  React DOM
1)  Create React App

1)  Which method creates and returns a React element of the given type?

1)  create()
1)  createNode()
1)  ReactDOM.render()
1)  createElement()

React creates actual DOM nodes.

False. React creates objects that describe DOM nodes.
True. React creates HTML elements that get rendered to the DOM.

Which method renders React elements to the DOM?

A
React.render()

B
DOM.render()

C
React.createElement()

D
ReactDOM.render()

React manipulates and updates the DOM directly.

True. React provides selector methods like getElementById() and querySelector() that let you select and manipulate elements.

False. React only manages what gets rendered to the DOM via ReactDOM.render. It's the job of render() to interpret the element objects and create DOM nodes out of them.

## Understanding JSX (4:08)

We could describe our application's UI by using the React.createElement method over and over again, it really is possible to do. However, it's not convenient. 0:11 It's a lot of extra typing, and all of those React.createElement calls make 0:15 things pretty confusing, especially when working with larger apps.

0:19 This is where JSX comes in. JSX is an extension to the to the JavaScript language 0:25 that uses mark-up-like syntax to create React elements. 0:28 Most React developers write their UI was JSX, 0:31 because as you'll see, it resembles writing HTML. 0:34 Now that you've gained an understanding of the React.element API, 0:39 I'll teach you how JSX is a simple abstraction on top of it.

0:42 So let's start by converting our createElement calls for 0:46 title and desc to JSX. 0:49 First, I'll replace the titles React.createElement function 0:54 with opening and closing h1 tags, and 0:59 the text My First React Element. 1:03 Then, replace React.createElement in the description with a set of p tags and 1:11 the text, I just learned how to create a React node and render it into the DOM.

1:18 Now, this isn't really HTML that we're writing, or actual JavaScript syntax. 1:24 This is JSX, a syntax extension to JavaScript, and you're going to use it a lot while working with React. 1:32 So let's save app.js and 1:35 head over to the console, refresh and notice how we get a syntax error. 1:41 JSX is not valid JavaScript, so the browser cannot interpret it. 1:46 To create React elements with JSX, 1:49 it needs to be transpiled into react.createElement calls. 1:53 We can use the Babel compiler to do this. 1:55 Normally during development, you'd have a build system set up with Babel in 1:59 a tool-like web pack to automatically process your JavaScript files.

2:02 For instance, the tool create app provides a built system out of the box to do this. 2:08 But it's also possible to use bubble directly in the browser via a script tag. In index.HTML, I'll add a script tag that points to Babel stand alone and 2:17 you can copy the script tag from the teachers notes with this video.

```HTML
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```

2:23 This is going to allow us to use JSX without a built step. 2:27 Now, there's one more thing we need to do in order for babel to work in the browser.

2:31 In the script tag to our app.js file, add the type text/babel. This signals to the babel script that the JavaScript and 2:44 app.js should be complied before being executed. I'll give this file a save and over in the console once I refresh, the error goes away. 2:55 And the same elements are displayed on the page. 2:57 You have a header, with the child h1 and p elements.

3:01 Keep in mind that in production you would not use this text/babel type attribute. 3:08 Most likely your code would already be recompiled using babel and a build tool like webpack before serving it to the browser.

3:15 Now JSX still produces objects that describe a DOM node. 3:21 For example, if I console.log(title), notice how 3:26 it's still the same object describing the h1 element like we saw earlier. 3:33 To demonstrate, I'll bring up the online Babel compiler or repl so 3:37 you can see how JSX gets to convert it to JavaScript. 3:40 I'll simply copy the title and desc variables from app.js and 3:46 paste them into this left panel. 3:49 Over in the right panel, we see that babel converts the JSX 3:52 into React.create element calls just like we wrote earlier. 3:57 So this should look a familiar to you. 3:59 During this course feel free at any time to copy and paste parts of your React code 4:03 into this online compiler to check out and learn what's happening under the hood.

Resources

- [Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)
- [JSX In Depth](https://reactjs.org/docs/jsx-in-depth.html)
- [Babel REPL](https://babeljs.io/repl)
- [JSX Represents Objects](https://reactjs.org/docs/introducing-jsx.html#jsx-represents-objects)

## Embed JavaScript Expressions in JSX (6:47)

Now let's finish converting our createElement calls to JSX. 0:04 JSX tags can contain children, or nested elements. 0:08 So to convert the parent header element, 0:11 I'll replace the value of the header variable with a set of parentheses, and 0:16 inside the parens, write opening and closing header tags. 0:21 I'm using parentheses to surround my JSX across multiple lines. 0:25 While it isn't required, it allows for good code style and readability. 0:29 So I also recommend that you wrap two or more lines of JSX in parentheses. 0:34 Next, I'll place my `h1` and `p` tags inside the header by simply copying 0:39 them from the variables above and pasting them inside the header. 0:48 As you'll see in the browser, rendering the same header into the DOM, 0:55 renders the same header element `h1` and `p` element to the page. 1:01 Now, looking at what this JSX compiles to with Double, you can see that 1:05 it's all React.createElement call behind the scenes. 1:11 And since JS acts as an extension to the JavaScript language, 1:15 it accepts any valid JavaScript expressions written inside curry braces. 1:19 This allows you to make your JSX more dynamic. 1:22 For example, I will set the value of the title and 1:26 desc variables to a string by replacing the h1 and p tags with quotes. 1:34 Then, I'll use the title, and desc variables inside the h1 and 1:39 p tags in the header by wrapping them in curly braces. 1:42 So first I'll replace the h1's text with a set of curry braces and 1:46 inside the curly braces references the title variable. 1:50 And right below in the paragraph, 1:53 I'll replace the text with a set of curly braces and write the desc variable. 1:59 And over in the browser, you can see that everything is still the same. 2:06 When you use curly braces in JSX, it's called a JSX expression. 2:12 A JSX expression is always surrounded by curly braces and it can be 2:17 placed between JSX tags like this or as the value of an attribute in the JSX tag. 2:23 So for example, I'll create a new variable named myTitleID and 2:31 set it to the string 'main-title'. 2:35 And now I can use the value assigned to myTitleID as the h1 ID value like so. 2:46 And if we inspect the h1 in the console, 2:49 we see that the ID attribute is set to main-title. 2:53 Good, so now let's make our static text 2:57 just a little bit more dynamic, with a JSX expression. 3:01 I'll create the variable name, and assign it the string 'Guil'. 3:09 Inside the H1, I'll replace the title variable 3:13 inside the curly braces with the name variable. 3:17 Then add an apostrophe 's after it and 3:22 the text First React Element. 3:26 Now, I'll go ahead and 3:27 delete the title variable up top since I'm no longer using it. 3:32 I'll give app.js a save, and over in the browser, once I refresh, 3:38 we see the text GUIL'S FIRST REACT ELEMENT as the title. 3:46 Just remember that wherever you're including the curly-braces, 3:50 you're exiting JSX and entering JavaScript territory. 3:54 The curly braces lets JSX know that you're writing JavaScript. 3:58 For example, you can do math operations with JSX expressions. 4:02 I'll create an input element and 4:05 set the value to a JSX expression that multiplies 10 by 20, 4:10 and over in the browser we see 200 as the input fields value. 4:16 And there are lots of other things you can do with JSX expressions which we'll 4:20 learn about in a later video. 4:22 But feel free to try writing a few expressions on your own 4:26 after this video to explore the capabilities of JSX. 4:29 Finally, there are a few other rules and 4:32 conventions to remember while working with JSX and React. 4:36 The main one is attribute names. 4:38 React uses a camel case property naming convention, 4:42 instead of the usual HTML attribute names. 4:45 For example, to apply a CSS class to an element, 4:49 use the attribute className instead of class. 4:54 JSX is not HTML, and because JSX code gets compiled to JavaScript, 5:00 React doesn't use class, but rather className for this attribute. 5:06 This is because class is a reserved word in JavaScript, 5:09 which is used to define classes. 5:11 Now, it may feel a bit strange at first, and 5:13 it could be something you'll forget about from time to time. 5:17 But as you can see, React translated class name into the class attribute, 5:22 when the element gets rendered to the page. 5:26 And finally, comments in JSX are also different from comments in JavaScript. 5:32 JSX requires you to place comments inside curly braces like this. 5:37 And this also works for multi-line comments. 5:54 Keep in mind that using JSX with React is optional. 5:58 But being able to declare and visualize your UI in a way that's like the HTML you 6:03 know and love, not only feels more natural, but it's also a whole lot 6:07 more convenient than writing endless React.create element functions. 6:12 As you're learning React, it might seem a little bit weird that you have what looks 6:16 like HTML mixed into your JavaScript. 6:18 Remember JSX is not HTML, 6:20 it really is an alternative syntax to calling functions in JavaScript. 6:26 So if the idea of JSX is a bit off putting to you right now, I ask you to keep 6:31 an open mind after becoming familiar with it, the benefits should become apparent. 6:35 Now React elements are just a small piece of a fundamental feature of React. 6:39 Components, so in the next stage, you'll start to build a React application 6:44 by first exploring the world of React components.

Resources

- [Embedding Expressions in JSX](https://reactjs.org/docs/introducing-jsx.html#embedding-expressions-in-jsx)
- [Babel REPL](https://babeljs.io/repl)

## JSX Review (6 questions)

Which of the following JSX snippets applies a class of 'container' to the div?

Choose the correct answer below:
A

<div class="container">...</div>

B

<div className="container">...</div>

C

<div class-Name="container">...</div>
