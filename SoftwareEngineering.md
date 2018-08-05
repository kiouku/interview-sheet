# Software engineering

## Polymorphism

### Definition
From type theory is the provision of a single interface to entities of different types

### Types

- Ad hoc polymorphism: when a function denotes different and potentially heterogeneous implementations depending on a limited range of individually specified types and combinations. Ad hoc polymorphism is supported in many languages using function overloading.
					
- Parametric polymorphism: when code is written without mention of any specific type and thus can be used transparently with any number of new types. In the object-oriented programming community, this is often known as generics or generic programming. In the functional programming community, this is often shortened to polymorphism.

- Subtyping (also called subtype polymorphism or inclusion polymorphism): when a name denotes instances of many different classes related by some common superclass.

### Implementations
Polymorphism can be distinguished by when the implementation is selected: statically (at compile time) or dynamically (at run time, typically via a virtual function). This is known respectively as static dispatch and dynamic dispatch, and the corresponding forms of polymorphism are accordingly called static polymorphism and dynamic polymorphism.</p>
				
- Static polymorphism executes faster, because there is no dynamic dispatch overhead, but requires additional compiler support. Further, static polymorphism allows greater static analysis by compilers (notably for optimization), source code analysis tools, and human readers (programmers).
- Dynamic polymorphism is more flexible but slower—for example, dynamic polymorphism allows duck typing, and a dynamically linked library may operate on objects without knowing their full type.

Static polymorphism typically occursy in ad hoc polymorphism and parametric polymorphism, whereas dynamic polymorphism is usual for subtype polymorphism. However, it is possible to achieve static polymorphism with subtyping through more sophisticated use of template metaprogramming, namely the curiously recurring template pattern.

- Examples static: templates/generics, function overloading, macros
- Examples dynamic: duck typing, dynamic dispatch with vtables (subtyping)


### Duck typing for polymorphism without (static) types
Duck typing is concerned with establishing the suitability of an object for some purpose, using the principle, "If it walks like a duck and it quacks like a duck, then it must be a duck." With normal typing, suitability is assumed to be determined by an object's type only. In duck typing, an object's suitability is determined by the presence of certain methods and properties (with appropriate meaning), rather than the actual type of the object.

## Testing

## Agile software development
- TDD
- BDD: 
- DDD: 
- SCRUM

## Design Patterns
- Behavioral
- Structural
- Creational
- Concurrency

## SOLID principles
- Single responsability principle
- Open/close principle
- Liskov substituion principle
- Interface segregation principle
- Dependency inversion principle
- bonus: YAGNI, KISS

## Conway's law
Organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations.

## Design smells
- Rigidity is the tendency of software to be difficult to change. 
- Fragility is the tendency of software to break in many places when a single change is made. 
- Immobility A design is immobile when it contains parts that could be useful in other systems, but the effort and risk of separating them from the original system are too great.
- Viscosity When faced with a change, developers often have several ways to implement the desired change.
- Needless repetition In short copy and pasting code throughout the system.
- Opacity Opacity is the tendency of a module to be difficult to understand. 
- Needless complexity This may very well be the most important smell of bad design.