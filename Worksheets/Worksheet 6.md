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

4. An electricity board charges according to following rates:

   For the first 100 units - 40 P per unit,

   For the next 200 units - 50 P per unit,

   Beyond 300 units - 60 P per unit.

   All users are charged a meter charge too, which is Rs 50/-

   Write a program in C to read the names of users and number of units consumed, and print out the charges with names.
   
 ```c  
#include <stdio.h> 
#include <string.h>
#define MAX 25 
int main() 
{ 
    char name[MAX]; 
    float bill_amount;
  
    printf("Enter your Name: \n"); 
    fgets(name,MAX,stdin); 
    printf("Enter the number unit used :");
    scanf("%f",&bill_amount);
    if(bill_amount<=100)
        printf("%s have to %.2f P",name,(bill_amount*40)+50);
    else if(bill_amount<=200)
         printf("\n%s have to %.2f P",name,(bill_amount*50)+50);
    else if(bill_amount>300)
         printf("\n%s have to %.2f P",name,(bill_amount*60)+50);
  
    return 0; 
} 
```

5. Write a program in C to read a number `x` and print ![](https://latex.codecogs.com/gif.latex?$$x^2,x^3,x^4,x^5$$)

```c
#include <stdio.h>
#include<math.h>

int main() 
{
    double num;
    
    printf("Enter a Number :\n");
    
    scanf("%lf",&num);
    
    printf("\n %.2lf\n %.2lf\n %.2lf\n %.2lf",pow(num,2),pow(num,3),pow(num,4),pow(num,5));
    
	return 0;
}
```

6. Write a program in C to accept three digits (i.e 0-9) and print all possible combinations from these digits. (for example, if the        three digits are 1, 2 and 3, then all possible values are 123, 132, 231, 213, 312 and 321)

```c
