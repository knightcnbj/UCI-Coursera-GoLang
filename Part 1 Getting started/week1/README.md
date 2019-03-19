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
