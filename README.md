### how to use gdb
```
g++ -g mos.cpp -o mos

gdb mos

break main
break 85

run

for inspecting memory
x/4xb mem.Data

    - x: gdb for examine memory
    - /4xb: format for display memory

print mem.Data + 0xFFFC


```