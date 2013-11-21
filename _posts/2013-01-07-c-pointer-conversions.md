---
layout: post
title: C Pointer Conversions
---

In C, pointers to a type may be converted to pointers to another type.

According to the current C Standard -- ISO/IEC 9899:2011:
> A pointer to an object or incomplete type may be converted to a pointer to a different object or incomplete type. If the resulting pointer is not correctly aligned for the pointed-to type, the behavior is undefined.

It basically means, that a pointer to a type that has more restrictive alignment requirements should never be converted to a pointer to a type that has less restrictive alignment requirements.

For example, in the case of a 64-bit system where `int` is aligned to 4 bytes, and `long` is aligned to 8 bytes, the conversion from `int*` to `long*` has undefined behavior.

```c
void func(void) {
    int i;
    long* lp;

    printf("\n%u", (unsigned int)sizeof(int));   /* 4 */
    printf("\n%u", (unsigned int)sizeof(long));  /* 8 */

    lp = (long*)&i;  /* This should be avoided! */
}
```

## Converting `void*` Pointers

Pointers to type `void` are pointers that point to a value that has no type, this allows `void*` pointers to point to any data type.

A pointer to any type may be converted to a pointer to `void` and back again to the original type without loss of information.

```c
void func(void) {
    int i;
    void* vp;
    int* ip;

    vp = (void*)&i;
    ip = (int*)vp; /* ip now contains the address of i */
}
```
