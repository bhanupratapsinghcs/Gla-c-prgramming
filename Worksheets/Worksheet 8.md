# Worksheet 8

1. Write a function in C named **SumFun()**, with arguments `n` and `N`, which returns the sum of the following series.
   ![](https://latex.codecogs.com/gif.latex?$$1-\frac{x^2}{2}+\frac{x^3}{3}-\frac{x^4}{4}+\frac{x^5}{5}-\frac{x^6}{6}+...+\frac{x^n}{N}$$)
   
```c
#include <stdio.h>
#include <math.h>

float SumNum(double x , int N);
 
int main()

{
	int N;
	double x;
 	
 	printf("Enter the value of x and N to get the sum ;\n");
 	scanf("%lf%d",&x ,&N);
 	
 	printf("\nSum of series is %.2f",SumNum(x,N));
 	
 	return 0;
 	
}
float SumNum(double x,int N)
{
	float sum = 1; 
	int i=2;
	while(i<=N)
	{
		if((i%2)== 0)
			sum -= pow(x,i)/i;
		else
			sum += pow(x,i)/i; 
		i++;
	}
	return sum;
} 
```
2. Write a function in C that converts a 2-digit `octal` number to `binary` number and prints the binary equivalent.

```c
#include <stdio.h>

void octal_to_binary(int octlnum );

int main()
{
	int octlnum;
	
	printf("Enter the octal number:\n");
	scanf("%d",&octlnum);
	
	octal_to_binary(octlnum);
	
	return 0;
	
}
void octal_to_binary(int octlnum)
{
	
	int rem,rev=0,temp;
	
	temp = octlnum;
	
	while(temp!=0)
	{
		rev=rev*10;
		rev = rev+temp%10;
		temp/=10;
	}
	
	octlnum = rev;
	
	while(octlnum != 0)
	{
		rem = octlnum%10;
		switch(rem)
		{
			case 0 : printf("000");
					break;
			case 1 : printf("001");
					break;
			case 2 : printf("010");
					break;
			case 3 : printf("011");
					break;
			case 4 : printf("100");
					break;
			case 5 : printf("101");
					break;
			case 6 : printf("110");
					break;
			case 7 : printf("111");
					break;
			default :printf("not an octal Number.");													
		}
		octlnum /=10;
	}
	
}

```

3. Write a function in C named **SumSequence()** with two arguments `double x` and `int n`. The function should return a value of type `double` and it should perform sum of the following series:

   ![](https://latex.codecogs.com/gif.latex?$$1-\frac{x}{1!}+\frac{x^2}{3!}-\frac{x^3}{5!}+\frac{x^4}{7!}...$$)

   up to n terms.

   **Note:** The symbol `!` represents *factorial* of a number i.e, `5! = 5 * 4 * 3 * 2 * 1`.

```c
#include <stdio.h>
#include <math.h>

double SumNum(double x , int N);
int factorial(int m);
 
int main()

{
	double  x;
	int N;
 	
 	printf("Enter the value of x and N to get the sum ;\n");
 	scanf("%lf%d",&x ,&N);
 	
 	printf("\nSum of series is %lf",SumNum(x,N));
 	
 	return 0;
 	
}
double SumNum(double x, int N)
{
	double sum = 1;
	int i=1,k=1;
	while(i<=N)
	{
		if((i%2)== 0)
			sum += pow(x,i)/factorial(k);
		else
			sum -= pow(x,i)/factorial(k); 
		i++;	 
		k+=2;
		//printf("k%d\n",k);
	}
	return sum;
} 
int factorial(int m)
{
	int j = 1,product = 1;
	//printf("m%d\n",m);

	while(j<=m)
	{
		product *= j++;
	}

	 m = product;
	 //printf("%d\n",m);
	 return m;
}
```

4. Write a function in C named **SumSum()** having parameters `X` of type `double` and `n` of type `int` with a result type as `double` to find the sum of the series given below.

   ![](https://latex.codecogs.com/gif.latex?$$X+\frac{X^2}{3!}+\frac{X^3}{5!}+...+\frac{X^n}{(2N-1)!}$$)

```c
#include <stdio.h>
#include <math.h>

double SumNum(double x , int N);
int factorial(int m);
 
int main()

{
	double  x;
	int N;
 	
 	printf("Enter the value of x and N to get the sum ;\n");
 	scanf("%lf%d",&x ,&N);
 	
 	printf("\nSum of series is %lf",SumNum(x,N));
 	
 	return 0;
 	
}
double SumNum(double x, int N)
{
	double sum = 0;
	int i=1,k=1;
	while(i<=N)
	{
		sum += pow(x,i)/factorial(k);
		//printf("sum %lf\n",sum);

		i++;	 
		k+=2;
	//	printf("k%d\n",k);
	}
	return sum;
} 
int factorial(int m)
{
	int j = 1,product = 1;
	//printf("m%d\n",m);

	while(j<=m)
	{
		product *= j++;
	}

	 m = product;
	 //printf("%d\n",m);
	 return m;
}
```

5.   Write a function that takes the time as three integer arguments (hours, minutes and seconds) and returns the number of seconds since the clock last "struck 12". Use this function to write a program to calculate the amount of time in seconds between two times, both of which are within one 12-hour cycle of the clock.

6.  Write a program to find the **LCM** and **GCD** of two numbers (using two functions).

7.  Write a program in C to print the sum of the following sequence

   ![](https://latex.codecogs.com/gif.latex?$$1+\frac{1}{1!}+\frac{2}{2!}+\frac{3}{3!}+...$$)

```c
#include <stdio.h>
#include <math.h>

double SumNum( int N);
double factorial(double m);
 
int main()

{
	int N;
 	
 	printf("Enter the value of x and N to get the sum ;\n");
 	scanf("%d",&N);
 	
 	printf("\nSum of series is %lf",SumNum(N));
 	
 	return 0;
 	
}
double SumNum( int N)
{
	double sum = 1;
	double i=1,k=1;
	while(i<=N)
	
	{
		sum = sum + i/factorial(k);
		//printf("i%d\n",i);
		//printf("sum %lf\n",sum);
		i++;	 
		k++;
		//printf("k%d\n",k);
	}
	return sum;
} 
double factorial(double m)
{
	int j = 1,product = 1;
	//printf("m%d\n",m);

	while(j<=m)
	{
		product *= j++;
	}

	 m = product;
	 //printf("%d\n",m);
	 return m;
}
```

8.  Write program in C to print the sum of the following sequence

   ![](https://latex.codecogs.com/gif.latex?$$1+\frac{x}{1!}+\frac{x^3}{2!}+\frac{x^5}{3!}+\frac{x^7}{4!}+...+\frac{x^{2n-1}}{n!}$$)
   
```c
#include <stdio.h>
#include <math.h>

double SumNum(double x , int N);
int factorial(int m);
 
int main()

{
	double  x;
	int N;
 	
 	printf("Enter the value of x and N to get the sum ;\n");
 	scanf("%lf%d",&x ,&N);
 	
 	printf("\nSum of series is %lf",SumNum(x,N));
 	
 	return 0;
 	
}
double SumNum(double x, int N)
{
	double sum = 1;
	int i=1,k=1;
	while(k<=N)
	{
		sum += pow(x,i)/factorial(k);
		//printf("sum %lf\n",sum);

		i+=2;	 
		k++;
	//	printf("k%d\n",k);
	}
	return sum;
} 
int factorial(int m)
{
	int j = 1,product = 1;
	//printf("m%d\n",m);

	while(j<=m)
	{
		product *= j++;
	}

	 m = product;
	 //printf("%d\n",m);
	 return m;
}
```

9.  Write a program in C having two value parameters `U` and `n` with result type `float` to find the sum of the series given below:

   ![](https://latex.codecogs.com/gif.latex?$$1-U+\frac{1}{2!}U^2-\frac{1}{3!}U^3+\frac{1}{4!}U^4+...\pm\frac{x^{2m-1}}{m!}$$)
 
```c
#include <stdio.h>
#include <math.h>

float SumNum(float x , int N);
int factorial(int m);
 
int main()

{
	float  U;
	int N;
 	
 	printf("Enter the value of U and N to get the sum ;\n");
 	scanf("%f%d",&U ,&N);
 	
 	printf("\nSum of series is %f",SumNum(U,N));
 	
 	return 0;
 	
}
float SumNum(float x, int N)
{
	double sum = 1;
	int i=1,k=1;
	while(i<=N)
	{
		if((i%2)== 0)
			sum += pow(x,i)/factorial(k);
		else
			sum -= pow(x,i)/factorial(k); 
		i++;	 
		k++;
		//printf("k%d\n",k);
	}
	return sum;
} 
int factorial(int m)
{
	int j = 1,product = 1;
	//printf("m%d\n",m);

	while(j<=m)
	{
		product *= j++;
	}

	 m = product;
	 //printf("%d\n",m);
	 return m;
}
```

10.  Raising a number `n` to a power `p` is the same as multiplying the `n` by itself `p` times. Write a function caller **power** that takes two arguments, a double value for `n` and int value for `p`, and returns the result as a double value. Use default argument of 2 for `p`, so that if this argument is omitted that number will be squared. Write the main function that gets value from the user to test power function.
```c

#include <stdio.h>
#include <math.h>
double power( double x ,int y);
int main()
{
	int p = 2;
	double n;
	printf("Enter the value of n:\n");
	scanf("%lf",&n);
	
	printf("Enter the value of p:\n");
	scanf("%d",&p);
	
	printf("Value of n after power function %.0lf",power(n,p));
	
	return 0;
	
}
double power(double x ,int y)
{
	int temp ,i = 1;
	temp = x;
	while(i<y)
	{
		x *=temp;
		i++;
	}
	return x;
}
```
