# Chapter 2: Program Structure

## Expressions and Statements

- An _expression_ is a fragment of code that produces a value<sup>[1](#nf1)</sup>
- The difference between an expression and a statement is not entirely clear.<sup>[2](#nf2)</sup>

## Bindings

You should imagine bindings as tentacles, rather than boxes.

```JavaScript
let caught = 5 * 5;
```

## The Environment

"The collection of bindings and their values that exist at a given time is called the environment."

## Functions

" A function is a piece of program wrapped in a value. "

## Controle Flow

"Here is the rather trivial schematic representation of straight-line control flow:"

![](/images/controlflow-straight.svg)

## Conditional Execution

"Not all programs are straight roads. We may, for example, want to create a branching road, where the program takes the proper branch based on the situation at hand. This is called conditional execution."

![](/images/controlflow-if.svg)

![](/images/controlflow-nested-if.svg)

---

<a name="fn1">1</a>: Every value that is written literally (such as 22 or "psychoanalysis") is an expression.

<a name="fn2">2</a>: The following is from the summary which is a little more helpful: You now know that a program is built out of statements, which themselves sometimes contain more statements. Statements tend to contain expressions, which themselves can be built out of smaller expressions.
