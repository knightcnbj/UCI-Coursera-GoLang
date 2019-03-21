Interfaces for Abstraction

1. Polymorphism
    1. ability for an obj to have different forms depending on the context
    2. ex: Area() for rectangle and triangle are diff
    3. it's usually done through inheritance in Java, but golang doesn't have inheritance

2. Interface
    1. use interface to do method loading
    2. ex: ```type Shape2D interface { Area() float64; Perimeter() float64}```
    3. now triangle and rectangle can implements interface method
    4. no explicit extends

3. Concrete type
    1. specify the exact representation of data and method
    2. complete method implementation is included
    3. similar to abstract class in java

4. Type assertion
    1. interface hides the diff between types

5. Error handling
    1. in go, it's common to return a pair (a, b) where a is the thing you want and b is the state (success or not)