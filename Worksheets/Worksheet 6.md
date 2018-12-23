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

2. Write a program in C (using a function) to accept a number and print its cube.
```c

#include <stdio.h>
#include <math.h>

void cube(double x);
int main() 
{
    double num ;
	printf("Enter a number to find it's cube : \n");
	
	scanf("%lf",&num);
	
	cube(num);
	
	return 0;
}
void cube(double x)
{
    printf("%.3lf",pow(x,3.0));
}

```
