# Harvard - CS50x

## Week 0 - Scratch

### Decimal vs Binary

- Human - 010
- Machine - 1010
- bits = binary digits
- 8 bits = 1 byte

### Representing Data

- Unicode uses decimal numbers to represent characters, symbols, emojis etc.
  - The computer then converts the decimal unicode to binary numbers

### Algorithms

- Basically, using maths to find solutions more efficiently

### Pseudocode

- Using human language aka informal symtax to represent the algorithm we want to write
- Actions, conditions, boolean, loops...



## Week 1 - C

```c
#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}
```

- \n = start a new line
- printf: f stands for "format"

### Compilers

- Converts source code to machine code (binary instructions that the computer understands)

```bash
# generates an output file named a.out from hello.c
$ clang hello.c
```

### String

```bash
$ clang -o hello hello.c
```

- -o flag is used to name the output file

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string name = get_string("What's your name?\n");
    printf("hello, %s\n", name);
}
```

- get_string is a function from cs50.h

```bash
# normally, we also need to include -lcs50 when compiling the above code
# however, we can make things easy by using "make" in terminal
# this generates an output file using the .c file name by default
make string
```

### Types, Formats, Operators

- There are other types we can use for our variables
  - `bool`, a Boolean expression of either `true` or `false`
  - `char`, a single character like `a` or `2`
  - `double`, a floating-point value with even more digits
  - `float`, a floating-point value, or real number with a decimal value
  - `int`, integers up to a certain size, or number of bits
  - `long`, integers with more bits, so they can count higher
  - `string`, a string of characters
- And the CS50 library has corresponding functions to get input of various types:
  - `get_char`
  - `get_double`
  - `get_float`
  - `get_int`
  - `get_long`
  - `get_string`
- For `printf` there are different placeholders for each type:
  - `%c` for chars
  - `%f` for floats, doubles
  - `%i` for ints
  - `%li` for longs
  - `%s` for strings
- And there are some mathematical operators we can use:
  - `+` for addition
  - `-` for subtraction
  - `*` for multiplication
  - `/` for division
  - `%` for remainder

### Syntaxes

#### Making Templates

```c
// When a placeholder is used, we need to define its value after a comma
printf("Your total is %f.\n", price * 1.0625);
```

#### For Loop

```c
#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("cough\n");
    }
}
```

#### Creating My Own Function

```c
#include <stdio.h>

void cough(int n);

int main(void)
{
    cough(3);
}

void cough(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("cough\n");
    }
}
```

#### While Loop

```c
// checks condition first then execute
while (true)
{
    printf("hello, world\n");
}
// execute first then checks condition
do
{
  n = get_int("%s", "Positive Integer: ");
}
while (n < 1);
```

#### If ... Else

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int n = get_int("n: ");

    if (n % 2 == 0)
    {
        printf("even\n");
    }
    else
    {
        printf("odd\n");
    }
}
```

### Memory, Imprecision, and Overflow

- Overflow happens when we don't have enough memory (bits)/ RAM to store all possible values
- Integer overflow is when a number gets so big that it runs out of bits and "rolls over", eventually becoming 0
- Y2K happened as programs used to store year with 2 digits only, same concept applies