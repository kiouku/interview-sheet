# Scala Job Interview Questions

This file contains a number of Scala interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [Language Questions](#language-questions)
  1. [Functional Programming Questions](#functional-programming-questions)
  1. [Reactive Programming Questions](#reactive-programming-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)
  1. [Answers](#answer)

#### General Questions:

* What did you learn yesterday/this week?
* Why and how did you start learning Scala?
* What excites or interests you about coding in Scala?
* What is a recent technical challenge you experienced and how did you solve it?
* Talk about your preferred development environment. (OS, Editor or IDE, Tools, etc.)
* What are your thoughts about the other JVM languages compared to Scala?
* Do you think that the Scala language and community is mature enough?

#### Language Questions:

* What is the difference between a `var`, a `val` and `def`?
* What is the difference between a `trait` and an `abstract class`?
* What is the difference between an `object` and a `class`?
* What is a `case class`?
* What is the difference between a Java future and a Scala future?
* What is the difference between `unapply` and `apply`, when would you use them?
* What is a companion object?
* What is the difference between the following terms and types in Scala: `Nil`, `Null`, `None`, `Nothing`?
* What is `Unit`?
* What is the difference between a `call-by-value` and `call-by-name` parameter? 
* How does Scala's `Stream` trait levarages `call-by-name`?
* Define uses for the `Option` monad and good practices it provides.
* How does `yield` work?
* Explain the implicit parameter precedence.
* What operations is a `for comprehension` syntactic sugar for?
* Streams:
	* What consideration you need to have when you use Scala's `Streams`? 
	* What technique does the Scala's `Streams` use internally?

#### Functional Programming Questions:

* What is a `functor`?
* What is a `applicative`?
* What is a `monad`?
  * What are the `monad` axioms?
  * What Scala data types are, or behave like, monads?
  * What are the basic and optional requirement/s to conform a Monad?
* Explain higher order functions.
* What is gained from using immutable objects?
* What is tail recursion?
  * How does it differentiate from common recursion?
  * What issues are there with tail recursive functions in the JVM?
  * How does the Scala compiler optimize a tail recursive function?
  * How do you ensure that the compiler optimizes the tail recursive function?
* What is function currying?
* What are implicit parameters?
* What are typeclasses?
* What are lenses?
* What is and which are the uses of: Enumerators, Enumeratees and Iteratee

#### Reactive Programming Questions:

* Explain the actor model.
* What are benefits of non-blocking (asynchronous I/O) over blocking (synchronous I/O).
* Do you think that Scala has the same async spirit as Node.js?
* Explain the difference between `concurrency` and `parallelism`, and name some constructs you can use in Scala to leverage both.
* What is the global ExecutionContext?
  * What does the global ExecutionContext underlay?
* Akka:
	* Which are the 3 main components in a Stream?

#### Coding Questions:

* How can you make a `List[String]` from a `List[List[String]]`?
* What is the difference (if any) between these 2 statements? 
```scala
  var x = immutable.Set[Int]()
  val y = mutable.Set[Int]()
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What testing framework for Scala do you use?
* What do you know about property based testing frameworks, such as Scalacheck?
* Do you like ‘scalaz‘?

#### Answers:

* [Scala interview questions](http://pedrorijo.com/blog/scala-interview-questions/) by [@pedrorijo91](https://github.com/pedrorijo91)


