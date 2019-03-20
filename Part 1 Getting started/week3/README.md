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
    