# Elm: A new approach to building the front end

## Agenda

* language Tour
* Application architecture
* Sample App
* How does it fit with a current project
* Tooling
* Sales Pitch

## Language Tour

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