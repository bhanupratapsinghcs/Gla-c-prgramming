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

2. Write a program in C to input a string and print its length.

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main()
{
	int x;
   char str[50];
   printf("Enter a string :\n");
   gets(str);
   x = strlen (str);
   printf("Size of string is %d",x);
   return 0;
}
```

3. Write a program in C to count the number of characters input by the user.

```c
#include <stdio.h>
#include <string.h>
int main()
{
	char str[50];
	
	int ctr = 0,len,i=0;
	
	printf("Enter the String :\n");
	
	gets(str);
	
	//for(i=0;i<50;i++)
	//	scanf("%c",&str[i]);
	
	i = 0;
	
	while(str[i]!='\0')
	{
		if(str[i]==' ')
		{
			//str[i]=str[i+1];
			ctr++;
			
		}
		i++;
		
	}
	len = strlen(str)-ctr;
	
	printf(" Number of characters in string is %d",len);
	
	return 0;
}
```

4. Write a program in C to find whether two strings contain equal number of characters.

```c
#include <stdio.h>
#include <string.h>
int main()
{
	int len1,len2;
	char str1[50],str2[50];
	
	printf("Enter first string:\n");
	gets(str1);
	
	printf("Enter second string:\n");
	gets(str2);
	
	len1 = strlen(str1);
	len2 = strlen(str2);
	if(len1==len2)
		printf("Strings have equal number of character.");
	else
		printf("Strings don't have equal number of character.");
		
	return 0;
		
}
```

5. Write a program in C to read marks to 50 students and store them in an array.

```c
#include <stdio.h>
#include <string.h>
int main()
{
	float marks[50];
	int i;
	printf("Enter Marks:\n");
	for(i = 0;i<50;i++)
	{
		printf("Enter mark of student %d\n",i+1);
		scanf("%f",&marks[i]);
	}
	
	for(i = 0;i<50;i++)
	{
		printf("Mark of student %d is %.2f\n",i+1,marks[i]);
		
	}
		
	return 0;
		
}
```
6. Write a program in C to check if a string is palindrome or not.

```c
#include <stdio.h>
#include <string.h>
int main()
{
	int check,i = 0;
	char str[50],str2[50];
	printf("Enter the string:\n");
	gets(str);
	while(str[i]!='\0')
	{
		str2[i]=str[strlen(str)-(i+1)];
		i++;
	}
	//puts(str2);		
	check = strcmp(str,str2);
	if (check==0)
		printf("String is a palindrome. ");
	else
		printf("String is not a palindrome. ");
	return 0;
}
```
7. Write a program in C to read the sales of 5 salesmen in 12 months and print the total sales made by each salesman.

```c
#include <stdio.h>
#include <string.h>
int main()
{
	int check,i = 0;
	char str[50],str2[50];
	printf("Enter the string:\n");
	gets(str);
	while(str[i]!='\0')
	{
		str2[i]=str[strlen(str)-(i+1)];
		i++;
	}
	//puts(str2);		
	check = strcmp(str,str2);
	if (check==0)
		printf("String is a palindrome. ");
	else
		printf("String is not a palindrome. ");
	return 0;
}
```
8. Write a program in C to illustrate working of call-by-value and call by value in a function.

```c
#include <stdio.h>
void call_by_value(int x, int y);
void call_by_ref(int *x,int *y);

int main()
{
		
	int x = 10, y = 20;
 
    printf("Initial value of x = %d\n", x);
    printf("Initial value of y = %d\n", y);
 
    printf("\nCalling the function\n");
 
   call_by_value(x, y);
 
    printf("\nValues after function call by value \n");
 
    printf("Final value of x = %d\n", x);
    printf("Final value of y = %d\n", y);
    
    call_by_ref(&x,&y);
    
    printf("\nValues after function call by reference \n");
    
	printf("Final value of x = %d\n", x);
    printf("Final value of y = %d\n", y);
    
}
void call_by_value(int x, int y)
{
    x = x + 10;
    y = y + 10;
 
    printf("\nValue of x (inside function) = %d\n", x);
    printf("Value of y (inside function) = %d\n", y);
}
void call_by_ref(int *x,int *y)
{
	*x = *x + 10;
    *y = *y + 10;
 
    printf("\nValue of x (inside function) = %d\n", *x);
    printf("Value of y (inside function) = %d\n", *y);
}
```
10. Write a program in C to print the largest number in an array (using a function).

```c
#include <stdio.h>

int largest_number(int *arr);

int main()
{
	int arr[10],i;
	printf("Enter 10 Numbers to find the greatest:\n");
	for( i = 0;i < 10; i++)
		scanf("%d",&arr[i]);
	
	printf("Largest number is %d",largest_number(arr));
	return 0;	
}

int largest_number(int *arr)
{
	int max,j = 0;
	max = *arr;
	
	while( j < 10 )
	{
		if(*(arr+j)>=max)
		{
			max = *(arr+j);
		}	
		j++;	
	}
	return max ;		
}
