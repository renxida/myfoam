# Associativity Measurement Code Diagram

```code
read performance counters

loop 3000 times:

    jmp 0x400 ; jump ahead 32 * 32-byte lines, to jump-target1
    db 0xFF, 0xFF, 0xFF ......; filler code until jump-target1

    jump-target1:
    jmp 0x400 ; jump ahead a further 32*32-byte lines to jump-target2
    db 0xFF, 0xFF, 0xFF ......; filler code until jump-target2

    jump-target:
    ... unrolled X times ...

read performance counters, take difference, and divide by 3000
```
