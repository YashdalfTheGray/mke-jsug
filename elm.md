# Elm: A new approach to building the front end

## Agenda

* language Tour
* Application architecture
* Sample App
* How does it fit with a current project
* Tooling
* Sales Pitch

## Language Tour

Elm compiles to Javascript and conceptually, it is similar to how ReactJS works.

Elm is a functional programming language. Any function in Elm takes in a parameter and spits out something; nothing else. All data in Elm is immutable. 

There is some syntactic sugar to create objects from other objects but variables can't be reassigned.

Functions - side effects + immutable data = performance improvements. 

Elm is also statically typed. You can also create your own type so you can create an entire type system depending on the business logic. 

Elm allows currying functions, can partially execute functions and return a function that takes the other parameters. It also supports recursion.

The pipe (`|`) operator makes it easier to read Elm code. The following code changes `message` to uppercase and repeats it 5 times. 

```elm
message
    |> toUpper
    |> repeat 5
```

## Application Architecture

### The model

Just like any data model.

```elm 
type alias Model = Int;
```

### Update

There are Actions that you can declare and use. They kind of behave like functions. 

The update action takes another action and takes a moded and returns the updated model.

```elm
actions = reset | ...

update : action -> model -> model
update action model = 
    ...
```

### View 

The view action takes the model and spits out HTML. That's the basic architecture of an Elm app. 

```elm
view : model -> Html
view model = 
    ...
```

All HTML elements in Elm contain 3 things, a valid HTML node, the attributes needed on the element and other HTML attributes that need to go on that node.

## Sample App

The sample app is a simple counter. It contains two actions, incement, decrement and the model is just an integer. 

## How does it fit?

It compiles to Javascript and the javascript source will be linked under the index.html. 

There are two ways you can pull in Elm, elm.fullsceen which takes the entire page and makes it the app. You can also use elm.embed which constricts it to one part of the page. 

The interop with Javascript is seamless through the `ports` type in Elm. It does this also by preseving the type safety. You can define actions and input/output types through the port and Elm will try its best to adapt the data.

## Tooling

### Compiler

The tooling gives you suggestions when it encounters an error. The compiler also outputs human-friendly errors and they encourage users to submit bug reports if the error encountered is not understandable.

### Package Manager

`elm-package` can be used to pull in packages. It will also ask you to add it to elm-package.json and add the dependencies. It will also do it politely.

### REPL

There is a time travelling debugger that records the app as time goes on. You can then pause the application and scrub back. You can also change parameters and it will make those changes live as you are scrubbing through the debugger history.


