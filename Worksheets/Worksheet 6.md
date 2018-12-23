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

3. Write a program in C to convert a given number of days into years, weeks and days.

```C

#include <stdio.h>

int main()
{
	unsigned int given_days,days,week,year;
	
	printf("Enter the number of days :\n");
	
	scanf("%u",&given_days);
	
	year = (given_days/ 365);
	week = (given_days % 365)/7;
	days = (given_days%365)%7;
	
	printf("Year = %d week = %d day = %d",year,week,days);
	return 0;
}
```
