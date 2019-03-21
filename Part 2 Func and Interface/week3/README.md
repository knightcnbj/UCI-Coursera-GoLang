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
