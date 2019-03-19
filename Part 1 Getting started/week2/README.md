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