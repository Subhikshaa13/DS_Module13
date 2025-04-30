Ex2 Conversion of the infix expression into postfix expression
DATE:29-4-2025
AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

Algorithm
Start the program.
Initialize a stack and set the top index to -1.
Define the push() and pop() functions to add and remove elements from the stack.
Define the priority() function to assign priorities to operators.
Traverse the expression in the IntoPost() function, handling operands, parentheses, and operators.
After processing the expression, pop and print any remaining operators from the stack.
End.
Program:
Program to convert the infix expression into postfix expression
```
#include<stdio.h> 
#include<ctype.h> 
 
char stack[100]; 
int top = -1; 
void push(char x) 
{ 
stack[++top]=x; 
}  
char pop() 
{ 
if(top==-1) 
return 0; 
else 
return stack[top--]; 
} 
int priority(char x) 
{ 
if(x=='(')
{ 
return 0; 
} 
if(x=='&'||x=='|') 
{ 
return 1; 
} 
if(x=='+'||x=='-') 
{ 
return 2; 
} 
if(x=='*'||x=='/'||x=='%') 
{ 
return 3; 
} 
if(x=='^') 
{ 
return 4; 
} 
return 0; 
} 
char IntoPost(char *exp) 
{ 
char *e,x; 
e=exp; 
while(*e!='\0') 
{ 
if(isalnum(*e)) 
{ 
printf("%c ",*e); 
} 
else if(*e=='(') 
{ 
push(*e); 
} 
else if(*e==')') 
{ 
while((x=pop())!='(') 
printf("%c ",x); 
} 
else 
{ 
while(priority(stack[top])>=priority(*e)) 
printf("%c ",pop()); 
push(*e); 
} 
e++; 
} 
while(top != -1) 
{ 
printf("%c ",pop()); 
}return 0; 
} 
int main() 
{ 
char exp[100]="3%2+4*(A&B)"; 
IntoPost(exp); 
return 1; 
} 
```
Output:
![image](https://github.com/user-attachments/assets/bd8ee92b-d92a-42ef-85f0-cc0fc982b7f8)


Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
