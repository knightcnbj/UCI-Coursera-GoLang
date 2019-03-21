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
    