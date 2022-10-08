## common gdb commands

- n = next (next line of execution)
- s = step (into a function call)
- c = continue (continue to next break point)
- r = run (run the program)
- bt = backtrace (print the stack frame structure. AKA: what line am I on, how did I get here?)
- info args = (print out all the arguements to the current stack frame)
- info local = (print out all the local variables in the current stack frame)
- info global = (print out all the global variables)




# flags: (gdb ```<flags>   <executable>```)
-x ```<filepath>``` (run file of gdb commands upon start of gdb)

## example file of gdb commands:
```gdb
b HashTable.c:158
b HashTable.c:151

define htbp
    b HashTable.c:$arg0
end
r --gtest_filter=Test_HashTable.Resize
```
What this does:
- set two break points
- define a new command that will make it easier to set new break points
  - example usage: htbp 387
  - effect, set a break point on line 387 of HashTable.c
- run the executable with those arguements.
