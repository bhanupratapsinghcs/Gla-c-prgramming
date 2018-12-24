# Worksheet 7

1. Write a program in C to input characters and change their case. (From lowercase to uppercase or vice versa.)

```c
#include<stdio.h>
int main()
{
  char ch;
  printf("Enter a character ;\n");
  scanf("%c",&ch);
  if(ch>=97)
    printf("%c",ch-32);
  else
    printf("%c",ch+32);
  return 0;  
}
```
