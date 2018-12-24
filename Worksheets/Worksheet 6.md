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


```

7. Write a program in C to read coordinates of two points and calculate the distance between them as per following formula:

   ![](https://latex.codecogs.com/gif.latex?$d=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2}$)
   
```c
#include <stdio.h>
#include<math.h>

int main() 
{
	float x1,x2,y1,y2,distance;
	printf("Enter the x coordinates of first point :\n");
	scanf("%f",&x1);
    printf("Enter the y coordinates of first point :\n");
	scanf("%f",&y1);
	printf("Enter the x coordinates of second point :\n");
	scanf("%f",&x2);
	printf("Enter the y coordinates of second point :\n");
	scanf("%f",&y2);
	distance = sqrt(pow(x1 - x2,2)+pow(y1 - y2,2));
	printf("Distance between two point is %.2f",distance);
	
	return 0;
}
```

8. Write a program in C to find the numbers when their sum (S) and product (P) is known. **Hint**: Use the quadratic equation

   ![](https://latex.codecogs.com/gif.latex?$x^2-Sx+P$)
   
```c   

#include <stdio.h>
#include <math.h>

int main() 
{
	float sum ,prod, diff,num1,num2;
	
	printf("Enter the Sum and Product :\n");
	
	scanf("%f %f",&sum,&prod);
	
	diff =sqrt(pow(sum,2)-(4*prod));
	
	num1 = (sum+diff)/2;
	
	num2 = sum-num1;
	
	printf("\nNumber are %.2f %.2f",num1,num2);
	
	return 0;
}
```

9. Write a program in C to create the equivalent of a four-function calculator. The program requires the user to enter two number and an    operator. It then carries out the specified arithmetic operation : addition, subtraction, multiplication or division of the two          numbers. Finally, it displays the result.

```c
#include <stdio.h>

int main() 
{
    double num1 , num2;
    char oprtr;
    printf("Enter the two numder :\n");
    scanf("%lf %c %lf",&num1,&oprtr ,&num2);
   // printf("Enter the operator(+,-,*,/):\n"); Don't know why it is not workking.
   // scanf("%[^\n]c",&oprtr);
    switch(oprtr)
    {
        case '+' : printf("%lf",num1 + num2);
                    break;
        case '-' : printf("%lf",num1 - num2);
                    break;
        case '*' : printf("%lf",num1 * num2);
                    break;                    
        case '/' : printf("%lf",num1 / num2);
                    break;
        default : printf("Enter the correct opertaor.");   
    }    
    /*if(oprtr=='+')
        printf("%lf",num1 + num2);
    else if(oprtr=='-')
        printf("%lf",num1 - num2);
    else if(oprtr=='*')
        printf("%lf",num1 * num2);
    else if(oprtr=='/')
        printf("%lf",num1 / num2);
    else
        printf("Enter the correct opertaor.");*/
        
    
	return 0;
}
