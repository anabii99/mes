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

### how to use lldb
- basic
```

clang++ -g mos.cpp -o mos

lldb mos

break 83

run

```
- for inspecting memory
```
x/4xb "mem.Data + 0xFFFC"

    - x: gdb for examine memory
    - /4xb: format for display memory

output gonna be like this, 0xA9 or 0xa9 it means we succesfully
operator overloading like "operator[]" to assign value into memory array

0x7fffffffd9f4: 0xa9 0x00 0x00 0x00

print mem.Data + 0xFFFC
(Byte *) $2 = 0x00007fffffffd9f4 "\xa9"

it had same memory with x/4xb
```

- better view with this 
```
memory read "mem.Data + 0xFFFC"

0x7fffffffd9f4: a9 00 00 00 00 00 00 00 00 00 00 00 01 00 00 00  ................
0x7fffffffda04: 00 00 00 00 4a 62 a4 f7 ff 7f 00 00 00 00 00 00  ....Jb..........

memory read --size 1 --format x --count 4 "mem.Data + 0xFFFC"
0x7fffffffd9f4: 0xa9 0x00 0x00 0x00
```
