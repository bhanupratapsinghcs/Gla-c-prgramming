# Worksheet 6  

1. Write a program in C to display the ASCII code of a character and vice versa.

```c
#include <stdio.h>

int main() {
    int a = 0;
    printf(" Ascii character set\n");
    while(a<128)
      printf("%d = %c\n",a++,a);
    return 0;
}
```

