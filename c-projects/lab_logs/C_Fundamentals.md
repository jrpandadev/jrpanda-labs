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
* The initial void means that the function does not return any values. The (void) means that no values are being provided to the function.
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

* **Note**:
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
* **Snippets**:
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
2. *Switch*:
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

3. *Ternary operator*:
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
    int a, b, t;
    scanf("%d%d", &a, &b);
    if (a < b)
    {
        t = a;
        a = b;
        b = t;
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
    int a, colindex, rs, rsq, rowindex=0, cs=0, m, n;
    scanf("%d,%d", &m, &n);
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
        rsq = rs * rs;
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
    for (int i = 1; i <= height; i++)
    {
        for(int j = 1; j < (i + 1); j++)
        {
          printf("*");
          printf(" ");
        }
    printf("\n");
    } 
}
```
```text
ii.       *
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
        scanf("%d", &height);
    }while(height < 1);
    for (int i = 1; i <= height; i++)
    {
        for(int j = 1; j <= height; j++)
        {
            if((j + i) > height)
            {
                printf("*");
                printf(" ");
            }
            else
                printf("  ");
        }
    printf("\n");
    } 
}
```
```text
iii.     * 
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
        scanf("%d", &height);
    }while(height < 1);
    for (int i=1; i <= height; i++)
    {
        for(int j = 1; j <= height; j++)
        {
            if((j + i) > height)
            {
                printf("*");
                printf(" ");
            }
            else
                printf(" ");
        }
    printf("\n");
    } 
}
```
```text
iv.       *  *  
        * *  * *
      * * *  * * *
    * * * *  * * * *
  * * * * *  * * * * *
```
```c
#include <stdio.h>
int main (void)
{ 
    int height;
    do{
        printf("Enter the height : ");
        scanf("%d", &height);
    }while(height < 1);
    for (int i = 1; i <= height; i++)
    {
        for(int j = 1; j <= height; j++)
        {
            if((j + i) > height)
            {
                printf("*");
                printf(" ");
            }
            else
                printf("  ");
        }
        printf("  ");
        for (int l = 0; l < i; l++)
        {
            printf("*");
            printf(" ");
        }
        
        printf("\n");
    } 
}
```
5. Implement a program in C that checks the validity of a given credit card number.
* **Note**:
1. *Luhn’s Algorithm* 
* According to Luhn’s algorithm, you can determine if a credit card number is (syntactically) valid as follows:

  1. Multiply every other digit by 2, starting with the number’s second-to-last digit, and then add those products’ digits together.
  2. Add the sum to the sum of the digits that weren’t multiplied by 2.
  3. If the total’s last digit is 0 (or, put more formally, if the total modulo 10 is congruent to 0), the number is valid!
* That’s kind of confusing, so let’s try an example with Jyoti’s Visa: 4003600000000014.

* For the sake of discussion, let’s first underline every other digit, starting with the number’s second-to-last digit:

* 4003600000000014

* Okay, let’s multiply each of the underlined digits by 2:

* 1•2 + 0•2 + 0•2 + 0•2 + 0•2 + 6•2 + 0•2 + 4•2

* That gives us:

* 2 + 0 + 0 + 0 + 0 + 12 + 0 + 8

* Now let’s add those products’ digits (i.e., not the products themselves) together:

* 2 + 0 + 0 + 0 + 0 + 1 + 2 + 0 + 8 = 13

* Now let’s add that sum (13) to the sum of the digits that weren’t multiplied by 2 (starting from the end):

* 13 + 4 + 0 + 0 + 0 + 0 + 0 + 3 + 0 = 20

* Yup, the last digit in that sum (20) is a 0, so Jyoti’s card is legit!

* So, validating credit card numbers isn’t hard, but it does get a bit tedious by hand. Let’s write a program.

2. Actually, that’s a bit of an exaggeration, because credit card numbers actually have some structure to them. All American Express numbers start with 34 or 37; most MasterCard numbers start with 51, 52, 53, 54, or 55 (they also have some other potential starting numbers which we won’t concern ourselves with for this problem); and all Visa numbers start with 4.
```c
#include <stdio.h>

int main(void)
{
    long credit, temp;
    int len = 0, n = 1, e = 0, f = 0;

    // 1. Check input is valid using standard long
    do
    {
       printf("Number: ");
       if (scanf("%ld", &credit) != 1) return 1; // Safety check for non-numeric input
       
       temp = credit;
       len = 0;
       while (temp > 0)
       {
        temp = temp / 10;
        len++;
       }
    }
    while (len < 1);

    // 2. Loop through digits using math instead of string indexing
    temp = credit;
    int first_digit, second_digit;

    for (int i = 1; i <= len; i++)
    {
        int d = temp % 10; // Get the last digit
        
        if (i == len) first_digit = d;
        if (i == len - 1) second_digit = d;

        if (n % 2 == 0) // Your 'e' logic for every second digit
        {
            d *= 2;
            if (d > 9)
            {
                e += (d / 10) + (d % 10);
            }
            else
            {
                e += d;
            }
        }
        else // Your 'f' logic for other digits
        {
            f += d;
        }
        
        temp /= 10; // Move to the next digit
        n++;
    }

    // 3. Final Branding Logic
    if ((e + f) % 10 != 0)
    {
        printf("INVALID\n");
        return 0; 
    }

    int first_two = (first_digit * 10) + second_digit;

    if ((len == 15) && (first_digit == 3) && (second_digit == 4 || second_digit == 7))
    {
        printf("AMEX\n");
    }
    else if ((len == 16) && (first_digit == 5) && (second_digit >= 1 && second_digit <= 5))
    {
        printf("MASTERCARD\n");
    }
    else if ((len == 16 || len == 13) && (first_digit == 4))
    {
        printf("VISA\n");
    }
    else
    {
        printf("INVALID\n");
    }

    return 0;
}
```
## Character Input and Output
1. getchar() fetches the next input character each time it is called, and returns that character as its value.
2. putchar() is used to write a single character to the standard output.
* Example : program which copies its input to its output one character at a time.
```c
#include <stdio.h>

int main(void)
{
    int c;
    c = getchar();

    while (c != EOF) {
        putchar(c);
        c = getchar();
    }
}
```
* EOF will be either -1 or 0. Modern C compilers define EOF in the stdio.h include file - so you should never define EOF in your code. In modern C, the value of EOF is -1, but you should just include stdio.h and use the pre-defined EOF constant to check for end of file.

* **Problems**:
1. Write a C program counts characters.
```c
#include <stdio.h>

int main(void) /* count lines in input */
{
    long nc;
    // In a newline press ctrl + z then press enter
    nc = 0;
    while ( getchar() != EOF)
            ++nc;
    printf("%ld\n", nc);
}
```
2. Write a C program counts lines in its input. Input lines are assumed to be terminated by the newline character \n.
```c
#include <stdio.h>

int main(void) /* count lines in input */
{
    int c, nl;

    nl = 0;
    while ((c = getchar()) != EOF)
        if (c == '\n')
            ++nl;
    printf("%d\n", nl);
}
```
3. The fourth in our series of useful programs counts lines, words, and characters, with the loose definition that a word is any sequence of characters that does not contain a blank, tab or newline.(This is a bare-bones version of the UNIX utility wc.)
```c
#include <stdio.h>

#define YES 1
#define NO  0

int main(void) /* count lines, words, chars in input */
{
    int c, nl, nw, nc, inword;

    inword = NO;
    nl = nw = nc = 0;
    while ((c = getchar()) != EOF) {
        ++nc;
        if (c == '\n' )
            ++nl;
        if (c == ' ' || c == '\n' || c == '\t' )
            inword = NO;
        else if ( inword == NO ) {
            inword = YES;
            ++nw;
        }
    }
    printf("%d %d %d\n", nl, nw, nc);
}
```
## Break
* It is sometimes convenient to be able to control loop exits other than by testing at the top or bottom. The break statement provides an early exit from for, while, and do, just as from switch. A break statement causes the innermost enclosing loop (or switch) to be exited immediately.

* Example : program removes trailing blanks and tabs from the end of each line of input.
```c
#include <stdio.h>
#define MAXLINE 1000

int main(void) /* remove trailing blanks and tabs */
{
  int n;
  char line[MAXLINE];

  while ((n = getline(line, MAXLINE)) > 0) {
    while (--n >= 0)
      if (line[n] != ' ' && line[n] != '\t'
        && line[n] != '\n')
          break;
    line[n+1] = '\0';
    printf("%s\n", line);
  }
}
```
## Continue
* The continue statement is related to break, but less often used; it causes the next iteration of the enclosing loop (for, while, do) to begin. In the while and do, this means that the test part is executed immediately; in the for, control passes to the re-initialization step. (continue applies only to loops, not to switch. A continue inside a switch inside a loop causes the next loop iteration.)

## Goto's and Labels
* C provides the infinitely-abusable goto statement, and labels to branch to. Formally, the goto is never necessary, and in practice it is almost always easy to write code without it. We have not used goto in this book.
* Nonetheless, we will suggest a few situations where goto's may find a place. The most common use is to abandon processing in some deeply nested structure, such as breaking out of two loops at once. The break statement cannot be used directly since it leaves only the innermost loop.

## Functions
* C and nearly all language developed since allow us to write functions, sometimes also known as procedures, methods, or subroutines.
* A function is a named block of code that performs a specific task. A function can take inputs (called parameters), execute a block of statements, and optionally return a result.
* *Why use functions ?*
* Because :-
  1. **Organisation**: functions help break up a complicated problem into more manageable subparts.
  2. **Simplification**: smaller components tends to be easier to design & debug.
  3. **Reusability**: It can be recycled; you only need to write them once you can use them as often as you need.

* **Function Declaration**:
* The first step to creating a fumction to declare it. This gives the compiler a heads-up that a user-written functions appear in the code. 
* Function declarations should always go to the top of your code, before you begin writting main().
* This is the standard form that every function declaration follows:
```text
return_type name(arguments); 
```
* *return_type* - is what kind of variable the function will output.
* *name* - function call.   
* *arguments* - comma separated set of inputs to your functions, each of which has a type and a name.
* Example :- int sum(int a, int b);

* **Function Definition**:

* A definition provides the actual implementation of the function. It includes the full code or logic that runs when the function is called.

* *Why is declaration needed?*

* If a function is defined after the main function or another function that uses it, then a declaration is needed before it is called. This helps the compiler recognize the function and check for correct usage.

* In short, the declaration introduces the function to the compiler, and the definition explains what it actually does.

* **Calling a Function**:
* Once a function is defined, you can use it by simply calling its name followed by parentheses. This tells the program to execute the code inside that function.

* Example:
```text
int sum(int a, int b);
int sum(int a, int b)
{
    int s = a + b;
    return s;
}
```
* **Function Miscellany**:-
* Function sometimes takes no input - In that case, we declare the function having a void argument type.
* Function sometimes don't have an output - In that case, we declare the function having a void return type.
* **Examples**:-
* Previous Question 4 ii. solution can written using functions - 
```c
#include <stdio.h>

int get_height(void);
void print_pattern(int height);

int main(void)
{
    int height = get_height();
    print_pattern(height);
    return 0;
}

int get_height(void)
{
    int height;
    do {
        printf("Enter the height : ");
        scanf("%d", &height);
    } while (height < 1);

    return height;
}

void print_pattern(int height)
{
    for (int i = 1; i <= height; i++)
    {
        for (int j = 1; j <= height; j++)
        {
            if ((j + i) > height)
            {
                printf("*");
                printf(" ");
            }
            else
                printf("  ");   // two spaces to align with "* "
        }
        printf("\n");
    }
}
```
* Previous Question 5 solution can written using functions - 
```c
#include <stdio.h>

int  get_length(long number);
void process_digits(long credit, int len,
                    int *first_digit, int *second_digit,
                    int *e, int *f);
int  luhn_valid(int e, int f);
void print_brand(int len, int first_digit, int second_digit);

int main(void)
{
    long credit;
    int len = 0;

    // 1. Check input is valid and get length
    do
    {
        printf("Number: ");
        if (scanf("%ld", &credit) != 1)
            return 1;   // non‑numeric input → same behaviour as before

        len = get_length(credit);
    }
    while (len < 1);

    // 2. Loop through digits and compute checksum + first digits
    int first_digit = 0, second_digit = 0;
    int e = 0, f = 0;

    process_digits(credit, len, &first_digit, &second_digit, &e, &f);

    // 3. Luhn validity check
    if (!luhn_valid(e, f))
    {
        printf("INVALID\n");
        return 0;
    }

    // 4. Final branding logic
    print_brand(len, first_digit, second_digit);

    return 0;
}

int get_length(long number)
{
    long temp = number;
    int len = 0;

    while (temp > 0)
    {
        temp = temp / 10;
        len++;
    }
    return len;
}

void process_digits(long credit, int len,
                    int *first_digit, int *second_digit,
                    int *e, int *f)
{
    long temp = credit;
    int n = 1;      // position counter (same logic as original)

    *e = 0;
    *f = 0;

    for (int i = 1; i <= len; i++)
    {
        int d = temp % 10;  // last digit

        if (i == len)       *first_digit  = d;
        if (i == len - 1)   *second_digit = d;

        if (n % 2 == 0)     // "e" logic for every second digit
        {
            d *= 2;
            if (d > 9)
            {
                *e += (d / 10) + (d % 10);
            }
            else
            {
                *e += d;
            }
        }
        else                // "f" logic for remaining digits
        {
            *f += d;
        }

        temp /= 10;
        n++;
    }
}

int luhn_valid(int e, int f)
{
    return ((e + f) % 10 == 0);
}

void print_brand(int len, int first_digit, int second_digit)
{
    int first_two = (first_digit * 10) + second_digit; // kept for same logic
    (void) first_two;  // suppress unused-variable warning (no logic change)

    if ((len == 15) && (first_digit == 3) &&
        (second_digit == 4 || second_digit == 7))
    {
        printf("AMEX\n");
    }
    else if ((len == 16) && (first_digit == 5) &&
             (second_digit >= 1 && second_digit <= 5))
    {
        printf("MASTERCARD\n");
    }
    else if ((len == 16 || len == 13) && (first_digit == 4))
    {
        printf("VISA\n");
    }
    else
    {
        printf("INVALID\n");
    }
}
```
## Problems
1. Write a program, print.c, that takes a string as input and prints it character-by-character.
```c
#include <stdio.h>

int main(void)
{
    int c;

    // Read one character at a time until the user presses Enter (\n)
    while ((c = getchar()) != '\n' && c != EOF)
    {
        putchar(c);    // Print the character we just read
        putchar('\n'); // Print a new line immediately after
    }

    return 0;
}
```
2.Write a program, reverse.c, that takes a string as input,
and reverses it.
```c
#include <stdio.h>

void reverse(void);

int main(void)
{
    printf("Enter text: ");
    reverse();
    putchar('\n'); // Newline at the end for clean output
    return 0;
}

void reverse(void)
{
    char c;
    
    // 1. Read a character
    c = getchar();

    // 2. If it's NOT the end of the line...
    if (c != '\n' && c != EOF)
    {
        // 3. ...Call this function again immediately (Recursion)
        reverse();

        // 4. Print the character ONLY after the function above returns
        putchar(c);
    }
}
```
2. Write a program, palindrome.c, that takes an integer as
input, and determines whether it is a palindrome (the same
backwards and forwards).
```c
// palindrome.c
#include <stdio.h>

int is_palindrome(int n);
int reverse_int(int n);

int main(void)
{
    int n;

    printf("Enter an integer: ");
    if (scanf("%d", &n) != 1)
        return 1;  // input error

    if (is_palindrome(n))
        printf("Palindrome\n");
    else
        printf("Not a palindrome\n");

    return 0;
}

// Return 1 if n is a palindrome, 0 otherwise
int is_palindrome(int n)
{
    if (n < 0)          // treat negative numbers as not palindromes
        return 0;

    return n == reverse_int(n);
}

// Reverse the digits of n and return the reversed number
int reverse_int(int n)
{
    int rev = 0;

    while (n > 0)
    {
        rev = rev * 10 + (n % 10);
        n /= 10;
    }

    return rev;
}
```
## Variable Scope 
* **Scope**: It is a characteristic of a variable that defines from which functions, that variable can be accessed.
* **Local Variable**: These can only be accessed within the function in which they are defined.
* **Global Variable**: These can only be accessed by any function in the program.

* *Why does ths distinction matter ?*
* For the most part local variables in C are **passed by values** in function calls.
* When a variable is passed by value, the callee recieves a copy of the passed variable itself,i.e., the variable in the caller is unchanged unless overwritten.

## Compiling

* We convert source code into machine code using a very special piece of software called a compiler. Today, we will be introducing you to a compiler that will allow you to convert source code in the programming language C into machine code.

* source code -> compiler -> machine code

* For example, you might have a computer program that looks like this:
```c
#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}
```
* A compiler will take the above code and turn it into the machine code that might look something like this:
```text
01010100 01001000 01001001 01010011
00100000 01001001 01010011 00100000
01000011 01010011 00110101 00110000
```
* **Note** that the above is only illustrative. The machine code for the problem above would be much longer.
* Compiling involves four major steps, including the following:
* First, **preprocessing** is where the header files in your code, designated by a # (such as #include <stdio.h>) are effectively copied and pasted into your file.
* Second, **compiling** is where your program is converted into assembly code.
* Third, **assembling** involves the assembler (a tool in the compiler toolchain) converting your assembly code into machine code. 
* Finally, during the **linking** step, pre-compiled machine code from your included libraries is combined with your code. The final executable file is then outputted.
---