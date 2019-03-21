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