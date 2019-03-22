1. Function:
    1. Reuse part of code
    2. Give meaningful name to funcionality
    3. Abstraction and hide the detail of implementation

2. How to declare func:
    1. void func with para: ```func foo(x int, y int) {}```
    2. void func without para: ```func foo() {}```
    3. void func with same type para: ```func foot(x, y int) {}```
    4. func with para returns an int: ```func foo(x int) int {return 1}```
    5. func with para returns multi int: ```func foo(x int) (int, int) {return 1, 1}```

3. Call by value / ref:
    1. Go is call by value, so arguments are copied to parameters
    2. pros of call by value: data encapsulation (safer), cons: copying time is costy especially for large object
    3. call by reference is not built in Go, but we can pass in a pointer to do this just like C / C++
    4. ex: ```func foo(y *int) {*y = *y + 1}```<br>
    ```func main() {x := 2; foo(&x); fmt.Print(x)}```
    5. pros of call by ref: copying ref is fast since we just copy the address in memory, cons is data encapsulation (value maybe changed)

4. Using Slice instead of Array:
    1. slice contains a pointer to array
    2. passing a slice copies the pointer
    3. ex:
        ```func foo(sli int) int {sli[0] = sli[0] + 1}```<br>
        ```func main() {a := []int{1, 2}; foo(a); fmt.Print(a)}``` we are declaring a slice in main, note there is not int in []
    


1. First Class Value
    1. functions are First-class, functions can be treated like other types
    2. functions can be created dynamically
    3. it can be passed as arguments and returned as values
    4. can be stored in data structures, ex: an array of func

2. Env of a function
    1. set of all names that are valid inside a func
    2. names defined locally, in the function
    3. also go is lexical scoping. so var defined in bigger scope is also accessable
    4. closure: env + func

3. Variadic(...) and Deferred:
    1. when the number of argu is unknown, you put ```...``` like in JS
    2. ex: ```func getMax(vals ...int) int{}```, vals is a slice
    3. call can be deferred until the surrounding func completes, used for clean up
    4. ex: ```defer fmt.Println("Bye")``` execute until main func completes when it's defined in main()
    5. but the argu of deferred call is evaluated immediately



OOP in Go

1. Class
    1. although go doesnt have class, but go supports OOP
    2. class: data fields and method combined
    3. obj is an instance of class with actual data

2. How do we associate func with data (what a class is)
    1. give receiver type to a func (specify the arg type)
    2. ex:<br> 
    ```type MyInt int```<br>
    ```func (mi MyInt) Double () int {reutrn int(mi * 2)}```<br>
    ```v := MyInt(3)```<br>
    ```v.Double()```<br>
    here we define a type called MyInt (which is int), and a func called Double() takes a MyInt type arg arg returns an int, associate this func with MyInt<br>
    ```v``` is passed implicitly to Double()
    but this is call by value (we make a copy of v)

3. Use Struct to compose data fields
    1. ex: ```type Point struct {x float; y float}```
    2. we can make struct as receiver type

4. Pointer receiver
    1. to solve the pass by value prob above
    2. we pass the ptr, ```func (p *Point) OffsetX(v float) {p.x = p.x + v}```
    3. notice we didnt do deref above, it's done auto
    4. also we dont need to do ref when calling it
    5. ex: ```p := Point{3, 4}; p.OffSetX(5)``` notice we didnt use &



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