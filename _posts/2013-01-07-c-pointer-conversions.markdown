---
layout: post
title: C Pointer Conversions
---

In C, pointers to one type may be converted to pointers to another type. A pointer to an object may be converted to a pointer to an object whose type requires less or equally strict storage alignment, and back again without change.

In many circumstances, <code class="inline-code">void</code> pointers are preferred. Pointers  to type <code class="inline-code">void</code> are pointers which point to a value which has no type, this allows <code class="inline-code">void</code> pointers to point to any data type. However in C++ (unlike in C) conversions from pointers to any type to pointers to type <code class="inline-code">void</code> require an explicit conversion.

Below is an example. The comments on the following code refer to a 64-bit architecture (Intel Core i7) and the MSVC Compiler:

{% highlight cpp %}#include <stdio.h>;

int main()
{
    const double d = 371564759.278651;

    // Pointers of different type have the same size:
    // 8 bytes on a 64-bit platform.
    printf("\n%u", (unsigned int)sizeof(double*)); // 8
    printf("\n%u", (unsigned int)sizeof(char*));   // 8
    printf("\n%u", (unsigned int)sizeof(void*));   // 8

    // Pointer conversions do not affect result
    printf("\n%f", *(double*)(char*)&d);  // 371564759.278651
    printf("\n%f", *(double*)(void*)&d);  // 371564759.278651
    printf("\n%f", *(double*)(float*)&d); // 371564759.278651
    printf("\n%f", *(double*)(long*)&d);  // 371564759.278651

    return 0;
}{% endhighlight %}

<p class="references">References:</p>
<p class='reference'>Brian W. Kernighan and Dennis M. Ritchie. The C Programming Language, Second Edition.</p>
