1. Concurrency
    1. in order to do parallel execution, you need multiple core / CPU
    
2. GoRoutines
    1. it's a thread in go
    2. many goroutines execute within a single OS thread
    3. go runtime scheduler determine the schedule of gorountines
    4. it's like a little OS inside a single OS thread
    4. logical processor is mapped to a thread 

3. Interleaving
    1. execution order of command in two programs is unknown
    2. interleaving happens at machine level instead of go level

4. Race condition
    1. outcome is determined by interleaving (result is undetermined)
    