# Library

**The doc/lib is subject to change**

We'll refer size as the number of cell needed to be equal to 0 after ret
Unspecified behaviour occurs when the size isn't met. 

Most of the macros deal with positive numbers (for portability reasons), for thoses you will need to invert the sign of your cell first, using the macro to invert sign in math.mbf.
You'll have also to handle yourself the tracking and changes it implies.
## conditions.mbf

```bf
IF(n) Behaviour: takes n, returns 1 if n != 0 and 0 else. Size : 2
IFN(n) Behaviour: takes n, returns 0 if n != 0 and 1 else. Size : 0
IFEQ(n, n2) Behaviour: takes n and n2, returns 1 if n == n2 and 0 else. Size : 5
IFNEQ(n, n2) Behaviour: takes n and n2, returns 0 if n == n2 and 1 else. Size : 5
IFSUP(n, n2) Behaviour: takes n and n2, returns 1 if n > n2 and 0 else. Size : 5
IFINF(n, n2) Behaviour: takes n and n2, returns 1 if n < n2 and 0 else. Size : 5
```

## io.mbf

```bf
PRINT Behaviour: takes no argument, supposes there's a null cell before and after the string, needs to be on the first null cell and after printing stays on the null terminator. Size : 0
READ(n) Behaviour: takes n, return a string based on the input of the user for the n chars: "\0STRING\0". Size : n + 2
READLN Behaviour: takes no argument, return a string entered by the user until a '\n' is met ('\n' excluded). Size : n + 8
```


## math.mbf

```bf
ADD(n, n2) Behaviour: takes n and n2 and returns their sum. Size : 0
SUB(n, n2) Behaviour: takes n and n2 and returns their difference. Size : 0
MUL(n, n2) Behaviour: takes n and n2 and returns their product. Size : 1
DIVMOD(n, n2) Behaviour: divides n by n2 and returns euclidian result and rest (in two different cells). Doesn't verify if n or n2 equals to 0 Size : 6

INVERTSIGN+(n) Behaviour: returns the opposite of n where n is positive. Size : 0
INVERTSIGN-(-n) Behaviour: returns the opposite of n where n is negative. Size : 0
```

## strings.mbf

```bf
BEGINSTRING Behaviour : takes no argument, supposes we are in the null terminator and brings to the null before the string
ENDINGSTRING Behaviour : takes no argument, supposes we are in the null cell before the string and brings to the null terminator
```
