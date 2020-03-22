clang hello.c : generate a.out executable (for assembly output)
clang -o hello hello.c : generate hello executable
int i = 0; : declare integer variable i
#include <stdio.h> : include standard input/ouput library
int main(void){} : create function
printf("hello, world\n"); : print formatted string
rm a.out : delete a.out file
clang -o string string.c -lcs50 : compile code and include "link" the cs50 library file
make string : compile the string.c file and include any necessary library
counter = counter + 1; : increment counter
counter +=1; : increment counter
counter++; : increment counter
if (x<y) {} : if condition
if (x<y) {} else {} : if/else condition
if (x<y) {} else if {x==y} else {} : if/elif/else condition
while (true) {} : while condition
for (int i = 0; i < 50; i++) {} : for condition
Data types : 
 - bool
 - char
 - double
 - float
 - int
 - long
 - string
printf markers : 
 - %c for chars
 - %f for floats, doubles
 - %i for ints
 - %li for longs
 - %s for strings
Maths ops : 
 - + addition
 - - subtraction
 - * for multiplication
 - / for division
 - % for remainder

Code exemple : 
```
#include <stdio.h>

int i = 0;
int main(void)
{
    printf("hello, world\n");
}
if (x < y)
{
    printf("x is less than y\n");
}
```

# Sandbox
https://sandbox.cs50.io/