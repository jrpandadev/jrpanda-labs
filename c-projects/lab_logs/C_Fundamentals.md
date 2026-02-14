## 💡What is C ?
* C is a general-purpose, machine-independent programming language, originally developed for UNIX but equally suited to applications of all kinds -- from operating systems to numerical programs and databases.

* It is a low-level language that works directly with the kinds of primitive objects most computers use-charters, numbers, addresses-and the arithmetic/ logical operations real machines provide.

* C has no inherent operations on composite objects (strings, arrays, lists, sets), no heap or garbage collection, and no I/O facilities. Everything beyond expressions and functions is handled by explicitly called library routines.

* **Variable** : It is the name of the memory location which stores some data.
* **Expressions** : It is the combination of values, variables, operators, functions.
* **Keywords** : Reserved words that has special meaning to the compiler.There are 32 keywords in C.

|||||||||
|:---|:---|:---|:---|:---|:---|:---|:---|
|`auto`|`continue`|`double`|`for`|`int`|`signed`|`struct`|`void`|
|`break`|`do`|`else`|`if`|`long`|`static`|`switch`|`while`|
|`case`|`default`|`enum`|`goto`|`register`|`sizeof`|`typedef`|`volatile`|
|`char`|`const`|`extern`|`float`|`return`|`short`|`union`|`unsigned`|

* **Compilation** : A computer program that translates C code into machine code.
```c
//compilation code
gcc hello.c
gcc .\a
```
* **Comments** : lines that are not part of a program.
    * Single Line : //
    * Multiple Lines : /* ---comments--- */ 

* **Header File** : In C programming, a header file is a file with the .h extension that contains declarations of functions, macros, and data types to be shared across multiple source files. Example: #include<stdio.h>

---

## Datatypes in C
* **char** :- It is a datatype used for variables that will store single characters.It always takes upto 1 byte - 8 bits.
  * Range: -128 - 127
  * **Signed Char** : 1 byte
  * **Unsigned Char** : 1 byte
  *     ---> Unsigned :- it is a qualifier, which effectively doubles the range of that type at a cost of diswallowing any negative value.
  *     --->Range : 0 - 255
* **int** :- It is a datatype used for variables that will store integers.
  * Range: -2^31 - (2^31)-1
  * **Signed int** : 2 byte
  * **Unsigned int** : 2 byte
  * **Short int** : 1 byte
  * **Unsigned short int** : 1 byte
  * **long int** : 4 byte
  * **Unsigned long int** : 4 byte
* **float** :- It is a datatype used for variables that will store floating-point values, also known as real numbers.It takes upto 4 byte.
* **double** :- It is a datatype used for variables that will store floating-point values, also known as real numbers.The doubles are double precission. It takes upto 8 byte.
* **string** :- It is a datatype used for variables that will store a series of characters like words,sentences,paragraph etc. which programmers typically call a string. 

---

## Escape sequence in C
* Escape sequence refers to character constansts with special meaning.They start  with '\' followed by a single character.

|**Sequence** |**Name**|**Example**|**Uses**|
|:---|:---|:---|:---|
|`\a`|`Alert(bell)`|`printf("\a")`|`Triggers a system beep or flash`|
|`\b`|`Backspace`|`printf("Abc\bd")`|`Prints "Abd"-> moves back and overwrites c`|
|`\f`|`Formfeed`|`printf("Page 1\fPage 2")`|`Used for Printers to start a new page`|
|`\n`|`Newline`|`printf("Hello\nWorld")`|`Moves the cursor to the start of the next line`|
|`\r`|`Carriage return`|`printf("12345\rABC")`|`Prints "ABC45"-> returns to the start of the current line`|
|`\t`|`Horizontal tab`|`printf("Name:\tBro")`|`Adds a standard horizontal space (usually 8 spaces)`|
|`\v`|`Vertical tab`|`printf("Top\vBottom")`|`Moves the cursor to the next vertical tab stop`|
|`\\`|`Backlash`|`printf("File: C:\\Users")`|`Prints a single \`|
|`\?`|`Question Mark`|`printf("Why\?")`|`Prints ?`|
|`\'`|`Single Quote`|`printf("\'A\'")`|`Prints 'A'`|
|`\"`|`Double Quote`|`printf("\"a\"")`|`Allows you to put quotes inside a string`|
|`\xhh`|`Hexadecimal`|`printf("\x41")`|`Prints 'A'(Since 41 is the hex code for A)`|
|`\ooo`|`Octal`|`printf("\101")`|`Prints 'A'(Since 101 is the octal code for A)`|
|`\0`|`Null Character`|`chr str[] = {'a','e','\0'}`|`Tells C exactly where a string ends`|

---

## Program Structure 
```c
#include <stdio.h> //this tells the compiler to include the standard input-output library.
int main (void)
//main() is a function.
{
    printf("Hello World!") //print is the function called to output from a c program. 
}
```
* **scanf** : In C, scanf stands for "scan formatted." It is a built-in function used to read input from the standard input (usually your keyboard) and store that data into variables.
* *The Basic Syntax*
> scanf("format_string", &variable);

* **Note**
* All c programs start by executing from first statement of the main function.
* Just as main() is a function, printf is a library function from the standard input-output library, which is why we inserted the statement #include<stdio.h>.
* There are 256 characters in C.
* 'A'-'Z' == 65 - 90
* 'a' - 'z' == 97 - 122
* '0' - '9' == 48 - 57

|||
|:---|:---|
|`%4.0f`|`4 character wide with no decimal digit`|
|`%4.1f`|`4 character wide with 1 decimal digit`|
|`%0.6f`|`request 6 decimal digit`|
|`%d`|`int`|
|`%o`|`octal`|
|`%x`|`hexadecimal`|
|`%c`|`characters`|
|`%s`|`character string`|
|`%%`|`for % itself`|
|`%f`|`float`|
|`lf`|`long  float or double`|
|`%p`|`pointers`|

* char c = A;
* printf("%d",c); ::output: 65

---

## Operators
* **Arithmetic** : +,-,*,/,%,^
* **Boolean** : True or False
    * **logical**: And(&&)
           * Or(||)
           * Not(!)

    * **Relational**: >,<,>=,<=,==,!=

* **Precedence Order**
* Top {high} ---> Bottom{low}

|**Operator class**|**Operator type**|**Operator**|**Associativity**|
|:---|:---|:---|:---|
||`Parenthesis`|`{},[],()->,.`|`Left to Right`|
|`Unary`|`Boolean Not, unary -, ~ ,++, --`|`!,-`|`Right to Left`|
|`Arithmetic`|`Multiply,divide,remainder`|`*,/,%`|`Left to Right`|
||`Add,Substract(binary)`|`+,-`|`Left to Right`|
|`Comparison`|`Relational Comparison`|`<,<=,>,>=`|`Left to Right`|
||`Equality Comparison`|`==`|`Left to Right`|
|`Logical Operators`|`Logical AND ,Logical OR`|`&&,\|\|`|`Left to Right`|
|`Assignment`|`Assignent`|` = `|`Right to Left`|
|`Comma`|`comma`|`,`|`Left to Right`|

* **Note**
* a % b gives integer remainder.
* a && b is of type int irresspective of type of a & b.

---

## Conditionals
* It allows your program to make decisions.
1. *if / if-else / if-elseif-else*
*  Syntax: 
```text
if(condition)
{
    < code >
}
elseif(condition)
{
    < code >
}
else
     {
         < code >
     }     
```
* WAP to convert Fahrenheit to Celsius
```c
#include<stdio.h>
int main(void)
{
    float c,f;
    printf("Enter Fahrenheit: ");
    scanf("%f",&f);
    c=(5.0/9.0)*(f-32.0);
    printf("celsius = %f",c);
}
```
* WAP to check whether given year a leap year
```c
#include<stdio.h>
int main(void)
{
    int y;
    printf("Enter Year: ");
    scanf("%d",&y);
    if ((((y % 4) == 0)&&(!((y % 100)== 0)))||((y % 400)==0))
        printf("Year %d is a Leap Year",y);
}
```
* **Snippets**
* *To convert lowercase to uppercase*
```text
main()
{ 
    char ch;
    if (ch >='a' && ch <= 'z')
         ch = ch - 'a' + 'A';  

}
```
* *To check whether a char is uppercase*
```text
main()
{ 
    char ch;
    if (ch >='A' && ch <= 'z')
         printf("Uppercase \n");  
}
```
* *To check whether a char is digit*
```text
main()
{ 
    char ch;
    if (ch >='0' && ch <= '9')
         printf("Digit \n");  
}
```
2. *Switch*
* C's switch() statement is a conditional statement that permits enumeration of discrete cases, instead of replying on Boolean expression.
* It is important to break between each case or you will "fall through" each case (unless that is desired behaviour)
Example :
```text
int x;
switch (x)
{
    case 1: printf("one! \n");
            break;
    case 2: printf("two! \n");
            break;
    case 3: printf("three! \n");
            break;
    default: printf("Sorry! \n");
}
```
* break is used to stop the iteration. If break is not used all cases from the case where condition is valid, will be executed(In this case, if x=1 and break is not there,it will print all cases )

|**if/if-else/if-elseif-if**|**switch**|
|:---|:---|
|`use boolean expression to make decision` |`use discrete case to make decision`|

3. *Ternary operator*
* Syntax: (condition)? statement : statement
Example : int x = (x==0) ? 5 : 6 

## Symbolic Constant 
* C provides a preprocessor directive <also called a macro> for creating symbolic constant.
* Syntax:
```text
#define NAME REPLACEMENT
```
* At the time program is compiled, #define goes through the code and replace the name with replacement.
* If #include is similar to copy/paste then #define is analog to find/replace.
* Example :#define PIE 3.14

## Loops
1. *for* :
* Syntax :
```text 
for ( initialisation ; condition ; increment)
{    
    statement
}
```
* Example : for (int i; i<=10; i++){---code---}

2. *while* :
* Syntax :
```text
while (condition)
{
    statement
}
```

3. *do-while* :
* Syntax :
```text
do{
    statement
}while(condition)
```

|**while**|**do-while**|**for**|
|:---|:---|:---|
|`Use when you want a loop to repeat an unknown number of times and possibly not at all.` |`Use when you want a loop to repeat an unknown number of times but atleast once`|`Use when you want a loop to repeat an discrete number of times, though you may not know the number of times of compilation`|

* **Iteration**: Each run of thr loop is called Iteration.
* **Loop invariant**: A propperty relating values of variables that holds at the beginning of each iteration of loop.
* ****

---

## Practice-Problems

1. Read two numbers and show their GCD as output.

```c
#include <stdio.h>
int main(void)
{
    int a,b,t;
    scanf("%d%d",&a,&b);
    if (a<b)
    {
        t=a;
        a=b;
        b=t;
    }
    while (b != 0)
    {
        t = a;
        a = b;
        b = t % b;
    }
    printf("GCD : %d\n",a);
}
```
2. Read a sequence of numbers until a -1 . Output the length of the longest contiguous increasing sub-sequence.
```c
#include <stdio.h>
int main (void)
{
  int prev, curr, len=0, maxlen=0;
  scanf("%d",&prev);
  if (prev != -1 )
  {
    len == 1;
    scanf("%d",&curr);

    while (curr != -1)
    {
        if (prev < curr)
            len = len+1;
        else
        {
            if(maxlen < len)
               maxlen = len;
            len = 1;
        }
        prev = curr;
        scanf("%d",&curr);
    }
    if (maxlen < len)
        maxlen = len;
  } 
  printf("length of the longest contiguous : %d",maxlen) 
}

```
3. Print the sum of the squares of the sum of numbers in each row in a matrix of order m * n.
```c
#include <stdio.h>
int main (void)
{
    int a,colindex,rs,rsq,rowindex=0,cs=0,m,n;
    scanf("%d,%d",&m,&n);
    while (rowindex < m )
    {
        rs = 0;
        colindex = 0;
        while (colindex < n)
        {
            scanf("%d",&a);
            rs = rs + a;
            colindex = colindex + 1;
        }
        rsq = rs*rs;
        cs = cs + rsq;
        rowindex = rowindex + 1;
    }
}
```
4. Show the Following Patterns:-
```text
i.*
  * *
  * * *
  * * * *
  * * * * *
```
```c
#include <stdio.h>
int main (void)
{ 
    int height;
    do{
        printf("Enter the height : ");
        scanf("%d",&height);
    }while(height < 1);
    for (int i=1;i<=height;i++)
    {
        for(int j=o;j<(i+1);j++)
        {
          printf("#");
        }
    printf("\n");
    } 
}
```


