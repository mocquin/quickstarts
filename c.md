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
do {} while 
comments : // this is c-commented
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
Boolean operators :
 - or : ||
 - and : &&
 - equal : == 
Functions : 
 - main function : int main(void)
 - prototype (must be place before any reference to that function): void cough(void);
 - void cough(int n) {}
 - return n;
Printing/format : 
 - %.2f : 2 floating point precision
Datatypes : 
 - int : 4 bytes == 32 bits = -2^31 to 2^31-1
 - unsigned int : unsigned is a qualifier, modifying the int range : 0 to 2^32-1
 - char : 1 byte == 8 bits == -128 to 127
 - float : 4 bytes == 32 bits 
 - doubles : 8bytes == 64 bits 
Type : 
  - void 
Declaration variable : 
 - int n;
 - int n, k, i;
Assingment variable : 
 - n = 8
Initialization variable : 
 - int n = 0;
Qualifiers :
 - short
 - long
 - const
 - unsigned
Loops :
 - while (true) {}
 - while (bool_expr) {}
 - do {} while (bool_expr) 
 - for (int i = 0; i <10; i++)
Boolean operators :
 - logical operators :
      - logical and &&
      - logical or ||
      - logical not !
 - relational operators : 
     - less than <
     - more than >
     - less or equal <=
     - greater or equal >=
     - equality ==
     - inequality !=
 
If else ternary notation : x is 1 if expr is true, else 0
`int x = (expr) ? 1 : 0 ` 
 
Switch case : 
```
switch(x)
{
case 1:
    printf("");
    break;
case 2:
    printf("");
    break;
default:
    printf("");
}



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

// Prompt user for positive integer
int get_positive_int(string prompt)
{
    int n;
    do
    {
        n = get_int("%s", prompt);
    }
    while (n < 1);
    return n;
}
```

# Sandbox
https://sandbox.cs50.io/




int main(void)
{
    int h = 0;
    while (h<1 || h>8)
    {
        h = get_int("Height: ");
    }
    
    for (int i=0; i<h; i++)
    {
        //printf("i is : %i\n", i);
        // first half
        for (int j=1; j<=h; j++)
        {
            //printf("j is : %i\n", j);
            if (j<h-i)
            {
                printf("-");
            }
            else
            {
                printf("#");
            }
        }
        printf("  ");
        // second half
        for (int j=0; j<h; j++)
        {
            //printf("j is : %i\n", j);
            if (j<=i)
            {
                printf("#");
            }
            else
            {
                printf("-");
            }
        }
        printf("\n");
    }
}
