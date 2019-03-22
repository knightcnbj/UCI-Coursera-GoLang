1. advantage of go
    1. runs really fast
        1. 3 levels of programming language: 1. machine lang, assembly lang, high level lang (C++, java, go , python) (ordered from fasted to slowest)
        2. compiled (C++, java, Go) vs interpreted (python)
    2. garbage collection: automatic memory management
    3. simpler objects

2. Object: weakly OOP
    1. Go use ```struct``` instead of ```class``` like C, and we can associated methods and field of data to it
    2. Like simplied version of ```class```
    3. No constructor, inheritence

3. Concurrency:
    1. Parallelism: difficulaties like when do task start / stop, what if one task needs data from another data, concurrent modification
    2. Concurrency: enables parallelism by management of task execution, comm between tasks and sync between tasks
    3. Go includes concurrency primitives
    4. ```Goroutines``` represent concurrent tasks
    5. ```Channels``` are used to communicate between tasks
    6. ```Select``` enables task sync

4. Workspace:
    1. src: source code files
    2. pkg: packages / libs
    3. bin: executables
    4. workspace dir defined by GOPATH env var (it's set during installation)
    5. there must be one oackage called ```main``` and it needs a main() to start



1. Pointer:
    1. it's an address to some data in memory (probably virtual memory)
    2. & returns the address of a var / func
    3. * returns data at an address (dereferencing, opposite to &)
    4. new() func creates a var and returns a ptr to the var, ex: ptr := new(int); ptr = 3;

2. Declariation:
    1. ```var x int; x = 5```;
    2. or in one step: ```x := 5```;

3. Scope of var:
    1. Go is lexically scoped using block
    2. bi >= bj if bj is defined inside bi, defined inside is transitive
    3. var accessible from bj if var declared in bi && bi >= bj

4. Deallocating space:
    1. when a var is no longer needed, it should be deallocated
    2. just like C if we dont, we gonna have memory leak
    3. Stack stores local var, and it's deallocate when function finished
    4. Heap stores more persistent data, so we need to release it mannually
    5. Interpreted lang use GC to do this, like JVM of java and interpreter of Python

5. Scan:
    1. scan reads user input
    2. takes a ptr as an arg
    3. typed data is writeen to ptr
    4. returns number of scanned items
    5. ex: <br>
        ``` var appleNum int``` <br>
        ```fmt.Printf("number of apples?")```<br>
        ```num, err := fmt.Scan(&appleNum)```<br>
        ```fmt.Printf(appleNum)```<br>


1. Array:
    1. fixed length series of elements of certain type, just like other lang's array

2. Slice:
    1. more often to use instead of array
    2. it's a window on an underlying array
    3. Pointer indicates the start of slice
    4. Length is the number of slements in the slice
    5. Capacity is maximum number of elements
    6. ex: ```arr := [...]string{"a", "b", "c", "d", "e"}; s1 := arr[1, 3]; s2 := arr[2, 5];``` (just like substring in other langs)
    7. only differen when u initialize a slice (```sli := int[]{1, 2, 3}```) there is nothing in [], cause in array there would be a number or ...
    8. using make to create a slice, ```sli = make([]int, 10, (optional cap))```
    9. we can use append() to increase size of slice

3. Hash table:
    1. nothing special, just like hash table in other lang
    2. creating hashmap: ```var idMap map[string]int; idMap = make(map[string]int)```

4. Struct:
    ```type struct Person {```<br>
        ```name string```<br>
        ```addr string```<br>
        ```phone string```<br>
    ```}```<br>
    ```var p1 Person```<br>
    ```p1 := new(Person)```<br>
    ```p1.name = "joe"```<br>
    ```x = p1.name```<br>
    


Protocols and Format

1.  Requests for Comments (RFC)
    1. def of internet protocols and formats
    2. example: HTML, URI (URL is a type of URI, Uniform Resource Identifier), HTTP
    3. Golang provide packages for common RFC, func encode and decode protocol format
