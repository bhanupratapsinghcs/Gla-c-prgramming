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
