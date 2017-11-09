# Legit

a simple language to learn programming

## Legit as a Programming Language:

Legit is designed to be a simple programming language for people to learn the concept of programming.

The way Legit achievement this is by restricting the usage of local variables and forced each logical segment be moduled into a small function. By doing so, each function will only contains very simple logic.

With the code teared down, Legit can be read and write with ease even with a small screen in the era of mobile phone.

## Examples

Before we start explaining the details, let's take a look at some examples.

### Example 1: Function Name, Input, Output

```php
Func: ex1;
In: a;                          # input variable a
Out: a;                         # output variable a
```

### Example 2: Default Value, Variable Operation

```php
Func: ex2;
In: a = 1;                      # default a be 1 if no input value is assigned
a = a + 2;                      # math operation expression
Out: a;
```

### Example 3: If, Else, While Loop

```php
Func: ex3;
In: a;
if a > 2: a = a + 3;            # if a is bigger than 2
else: a = a + 1;                # if a is not bigger than 2
while a < 3: a = a + 1;         # a keeps adding 1 while a is smaller than 3
Out: a;
```

### Example 4: Multiple Input Variables

```php
Func: ex4;
In: a, b;                               # initiate 2 variables
while a < 3: a = a + 1, b = b - 1;      # 2 operations in 1 condition
Out: a + b;
```

### Example 5: No Input, Calling Another Function

```php
Func: ex5;
Out: ex2();             # output = 3
```

## 

## Function Name

The name of the function is defined in `Func:`.

```php
Func: function_name;
```

In this case, the name of the function is `function_name`.

Function name can only contains words, numbers and `_`.

Chars such as `SPACE` and `+-*/\|'"~!@#$%^&()[]{}<>?:;.,` are NOT allowed as the name of a function.

## Input and Output

### Input: `In:`

In input declaration, multiple variables can be defined and all variables must be defined in the input `In:`.

Programmers will need to create a new function to separate local variables.

A default value can be assigned to a variable while initiating.

```php
Func: test;
In: a = 0, b = 0;
Out: a * 3 + b * 2;
```

In this case, `test()` is `0`, `test(1)` is `3`, and `test(1, 1)` is `5`.

Variables will be taken in one by one and can NOT be assigned in another order.

Variable name can only contains words, numbers and `_`.

Chars such as `SPACE` and `+-*/\|'"~!@#$%^&()[]{}<>?:;.,` are NOT allowed as the name of a variable.

If the function do NOT need any variable, there is no need for the input line.

```php
Func: return_1;
Out: 1;
```

Note that `In:` is optional, if `In:` is used, at least one variables will need to be defined. `In: ;` is NOT Legit.

However, whether the function have `In:` or not, a function should always be called with a `()`.

```php
a = return_1();
```

### Output: `Out:`

Output is necessary for a Legit function.

A function always need to return something. `Out: ;` is not Legit.

Output can return a mathametical operation of some variables.

```php
Func: sum_1_2_3;
Out: 1 + 2 + 3;
```

Output can only return one variable. Vector can be used when multiple variables need to be returned.

```php
Func: return_1_2_3;
Out: [1, 2, 3];
```

Multiple output variables from a function can be assigned to one single variables.

```php
Func: sum_1_2_3_vector;
In: a = return_1_2_3();
Out: a[0] + a[1] + a[2];
```

In this case, variable `a` will become a vector.

## Variable

Variables in Legit has three different Types, `NUMBER`, `STRING`, or `VECTOR`.

### Number:

```php
a = 0;                                  # a = 0
b = 1 + 2;                              # b = 3
c = 3.14159;                            # c = 3.14159
d = 99999999999999999;                  # d = 99999999999999999
```

In Legit, there is no difference in Integer, Floating Number, or Long Number.

The precision of a number is limited to `2^63`, roughly 17 digits.

### String:

```php
a = "this is a string";                 # a = "this is a string"
b = "another" + " " + "string";         # b = "another string"
c = a[0];                               # d = "t"
```

String will always be inside a pair of double-quotes `""`.

Each character in a string is still considered to be a string. `[N]` can be used to indicate the `N+1`th element in the string, which is a string with only one character.

### Vector:

```php
a = [];                                 # a = []
b = [0, 1, 2];                          # b = [0, 1, 2]
c = ["0", "1", "2"];                    # c = ["0", "1", "2"]
d = [0, 1, 2, "0", "1", "2"];           # d = [0, 1, 2, "0", "1", "2"]
e = [[0, 1, 2], ["0", "1", "2"]];       # e = [[0, 2, 3], ["0", "1", "2"]]
```

Vector is an array of variables, and can only be created using `[]`.

The variables inside a vector can be a Number, a String, or a Vector.

A vector without any variable can be defined with `[]`;

## Variable Operation

```php
In: a = 1, b = 1;
a = 3;                                  # a = 3
a = a + 1;                              # a = 4
a = b;                                  # a = 1
b = a;                                  # b = 1
```

Operations will be run through one by one in Top-Down order.

In a line of Variable Operation expression, there can only contain one value assignment `=`.

Operations that will generate each data type will be listed below.

### Number:

`+` will add the two numbers. If the first variable is a Number and the second variable is not, the compiler will throw an error.

```php
In: a = 1, b = 1;
Out: a + b;                             # Out: 2
```

`-` will minus the first number by the second number.

```php
In: a = 2, b = 1;
Out: a - b;                             # Out: 1
```

`*` will multiply the two numbers.

```php
In: a = 2, b = 3;
Out: a * b;                             # Out: 6
```

`/` will divide the first number by the second number.

```php
In: a = 6, b = 2;
Out: a / b;                             # Out: 3
```

`^` will times the first number by the power of the second number.

```php
In: a = 2, b = 3;
Out: a ^ b;                             # Out: 8
```

`num()` function can be used to parse a string into a Number-type variable.

```php
Out: num("12345");                      # Out: 12345
```

`size()` function can calculate the length of a vector.

```php
Out: size([1, 1, 1, 1, 1]);             # Out: 5
```

### String:

`+` will add two strings together in to one string. If the first variable is a String and the second variable is not, the compiler will throw an error.

```php
In: a = "this is ", b = "legit";
Out: a + b;                             # Out: "this is legit"
```

The index of String starts from `0`.

`[N]` can indicate the `N+1`th element in the string.

```php
In: a = "01234";
Out: a[2];                              # Out: "2"
```

`str()` function can be used to transform a variable into a String-type variable.

```php
Out: str(12345);                        # Out: "12345"
```

`inverse()` will inverse the order of characters in a string from left to right.

```php
Out: inverse("legit");                  # Out: "tigel"
```

`takeLeft(, N)` will take the first `N` numbers of characters.

```php
Out: takeLeft("legit", 3);              # Out: "leg"
```

`takeRight(, N)` will take the last `N` numbers of characters.

```php
Out: takeRight("legit", 3);             # Out: "git"
```

`dropLeft(, N)` will drop the first `N` numbers of characters.

```php
Out: dropLeft("legit", 3);              # Out: "it"
```

`dropRight(, N)` will drop the last `N` numbers of characters.

```php
Out: dropRight("legit", 3);             # Out: "le"
```

### Vector:

If the first variable is a Vector, `+` will push the second variable into the vector after the last element.

```php
In: a = [0, 1], b = 2;
Out: a + b;                             # Out: [0, 1, 2]
```

```php
In: a = [0, 1], b = "2";
Out: a + b;                             # Out: [0, 1, "2"]
```

```php
In: a = [0, 1], b = [2, 3];
Out: a + b;                             # Out: [0, 1, [2, 3]]
```

`++` can concate two Vectors. Binding the head of the second Vector to the tail of the first Vector.

```php
In: a = [0, 1], b = [2, 3];
Out: a ++ b;                            # Out: [0, 1, 2, 3]
```

The index of Vector starts from `0`.

`[N]` can indicate the `N+1`th element in the vector.

```php
In: a = [0, 1, 2, 3];
Out: a[2];                              # Out: 2
```

Unlike String, elements getting from Vector will not necessary be a Vector.

`inverse()` will inverse the order of the elements in the Vector from left to right.

```php
Out: inverse([0, 1, 2, 3]);             # Out: [3, 2, 1, 0]
```

`takeLeft(, N)` will take the first `N` numbers of elements.

```php
Out: takeLeft([0, 1, 2, 3], 3);         # Out: [0, 1, 2]
```

`takeRight(, N)` will take the last `N` numbers of elements.

```php
Out: takeRight([0, 1, 2, 3], 3);        # Out: [1, 2, 3]
```

`dropLeft(, N)` will drop the first `N` numbers of elements.

```php
Out: dropLeft([0, 1, 2, 3], 3);         # Out: [3]
```

`dropRight(, N)` will drop the last `N` numbers of elements.

```php
Out: dropRight([0, 1, 2, 3], 3);        # Out: [0]
```
