# Functional Programming

## Lambda Expression

### Definition

A lambda is just an anonymous function - a function defined with no name. Essentially a lambda is a block of code that can be passed as an argument to a function call.

Lambdas usually define closures.

In some way function pointers or inner classes can achieve the same expression.

Extra:
The term "lambda" is short for lambda expression, and a lambda is just that: an expression. As such, it exists only in a program's source code. A lambda does not exist at runtime.

The runtime effect of a lambda expression is the generation of an object. Such objects are known as closures.

The distinction between a lambda and the corresponding closure is precisely equivalent to the distinction between a class and an instance of the class. A class exists only in source code; it doesn't exist at runtime. What exists at runtime are objects of the class type.  Closures are to lambdas as objects are to classes. This should not be a surprise, because each lambda expression causes a unique class to be generated (during compilation) and also causes an object of that class type--a closure--to be created (at runtime).

## Closure

### Definition

A closure is any function which closes over the environment in which it was defined. This means that it can access variables not in its parameter list.

## High order function

### Definition

It is a function that does at least one of the following:

- takes one or more functions as arguments (i.e. procedural parameters),
- returns a function as its result.

## Monad

### Definition

A monad is an "amplifier" of types that obeys certain rules and which has certain operations provided.

- First, what is an "amplifier of types"? By that I mean some system which lets you take a type and turn it into a more special type. For example, in C# consider Nullable<T>. This is an amplifier of types. It lets you take a type, say int, and add a new capability to that type, namely, that now it can be null when it couldn't before. As a second example, consider IEnumerable<T>. It is an amplifier of types. It lets you take a type, say, string, and add a new capability to that type, namely, that you can now make a sequence of strings out of any number of single strings.

- What are the "certain rules"? Briefly, that there is a sensible way for functions on the underlying type to work on the amplified type such that they follow the normal rules of functional composition. For example, if you have a function on integers, say

int M(int x) { return x + N(x * 2); }
then the corresponding function on Nullable<int> can make all the operators and calls in there work together "in the same way" that they did before.

(That is incredibly vague and imprecise; you asked for an explanation that didn't assume anything about knowledge of functional composition.)

- What are the "operations"?

- There is a "unit" operation (confusingly sometimes called the "return" operation) that takes a value from a plain type and creates the equivalent monadic value. This, in essence, provides a way to take a value of an unamplified type and turn it into a value of the amplified type. It could be implemented as a constructor in an OO language.

- There is a "bind" operation that takes a monadic value and a function that can transform the value, and returns a new monadic value. Bind is the key operation that defines the semantics of the monad. It lets us transform operations on the unamplified type into operations on the amplified type, that obeys the rules of functional composition mentioned before.

- There is often a way to get the unamplified type back out of the amplified type. Strictly speaking this operation is not required to have a monad. (Though it is necessary if you want to have a comonad. We won't consider those further in this article.)

## Referencial transparency

### Definition

Referential transparency, referred to a function, indicates that you can determine the result of applying that function only by looking at the values of its arguments i.e. pure function can safely be replaced by its expression.

## Pure functions

### Definition
A pure function is a function where the return value is only determined by its input values, without observable side effects.
