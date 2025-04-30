# EX 1 Display operator precedence in the infix expression.
## DATE:30-4-2025
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Start the program.Define the priority() function to return the priority of operators.
2. Initialize the string containing operators and operands. 
3. Loop through each character in the string. 
4. For each operator, call the priority() function to determine its priority. 
5. Print the operator and its corresponding priority level.
6. End the program. 

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression

#include <stdio.h> 
#include<string.h> 
int priority(char x) 
{ 
if(x == '&' || x == '|') 
return 1; 
if(x == '+' || x == '-') 
return 2; 
if(x == '*' || x == '/' || x == '%') 
return 3; 
if(x == '^') 
return 4; 
return 0; 
} 
int main() 
{ 
int i,j;
char ch[100]="(A*B)^C+(D%H)/F&G"; 
for(i=0;i<strlen(ch);i++) 
{ 
if(ch[i]=='+'|| 
ch[i]=='-'|| 
ch[i]=='*'|| 
ch[i]=='/'|| 
ch[i]=='%'|| 
ch[i]=='^'|| 
ch[i]=='&'|| 
ch[i]=='|') 
{ 
j=priority(ch[i]); 
switch(j) 
{ 
case 1: 
printf("%c ---- > ",ch[i]); 
printf("Lowest Priority\n"); 
break; 
case 2: 
printf("%c ---- > ",ch[i]); 
printf("Second Lowest Priority\n"); 
break; 
case 3: 
printf("%c ---- > ",ch[i]); 
printf("Second Highest Priority\n"); 
break; 
case 4: 
printf("%c ---- > ",ch[i]); 
printf("Highest Priority\n"); 
break; 
} 
} 
}  
return 0; 
}
 
*/
```

## Output:
![image](https://github.com/user-attachments/assets/e3c9d048-b18e-431f-bb5e-d14c1723b9bf)




## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
