# Legit

a simple language to learn to programme

## Legit as a Programming Language:

Legit is designed to be a simple programming language for people to learn the concept of programming.

By restricting the use of local variables and forced each logical segment to be modulized into a small function, each function will only contain very simple logic.

With the code torn down, Legit can be read and write with ease even with a small screen in the era of the mobile phone.

## Examples

Before explaining the details, here are some examples.

### Example 1: Function Name, Input, Output

```php
Func: ex1;
In: a;                                  # input variable a
Out: a;                                 # output variable a
```

### Example 2: Default Value, Variable Operation

```php
Func: ex2;
In: a = 1;                              # default a be 1 if no input value is assigned
a = a + 2;                              # math operation expression
Out: a;
```

### Example 3: If, Else, While Loop

```php
Func: ex3;
In: a;
if a > 2: a = a + 3;                    # if a is bigger than 2
else: a = a + 1;                        # if a is not bigger than 2
while a < 3: a = a + 1;                 # a keeps adding 1 while a is smaller than 3
Out: a;
```

### Example 4: Multiple Input Variables, Vector Output

```php
Func: ex4;
In: a, b;                               # initiate 2 variables
while a < 3: a = a + 1, b = b - 1;      # 2 operations in 1 condition
Out: [a, b];                            # vector output
```

### Example 5: No Input, Calling Another Function

```php
Func: ex5;
Out: ex2();                             # output = 3
```

## Comment

In a line of Legit, everything after `#` does NOT count.

```php
Func: test_function;                    # this does not count
In: a = 1;                              # this also does not count
a = a + 1;                              # bla bla bla
Out: a;                                 # still does not count
```

## Function Name

The name of the function is defined in `Func:`.

```php
Func: function_name;
```

In this case, the name of the function is `function_name`.

Function names can only contain words, numbers and `_`.

Chars such as `SPACE` and `+-*/\|'"~!@#$%^&()[]{}<>?:;.,` are NOT allowed as the name of a function.

## Input and Output

### Input: `In:`

In input declaration, multiple Variables can be defined and all Variables must be defined in the input `In:`.

Programmers will need to create a new function to separate local Variables.

A default value can be assigned to a Variable while initiating.

```php
Func: test;
In: a = 0, b = 0;
Out: a * 3 + b * 2;
```

In this case, `test()` is `0`, `test(1)` is `3`, and `test(1, 1)` is `5`.

Variables will be taken in one by one and can NOT be assigned in another order.

Variable names can only contain words, numbers and `_`.

Chars such as `SPACE` and `+-*/\|'"~!@#$%^&()[]{}<>?:;.,` are NOT allowed as the name of a Variable.

If the function does NOT need any Variable, there is NO need for the input line.

```php
Func: return_1;
Out: 1;
```

Note that `In:` is optional, if `In:` is used, at least one Variables will need to be defined. `In:;` is NOT Legit.

However, whether the function has `In:` or NOT, a function should always be called with a `()`.

```php
a = return_1();
```

### Output: `Out:`

An Output is necessary for a Legit function.

A function always needs to return something. `Out:;` is NOT Legit.

Output can return a mathematical operation of some Variables.

```php
Func: sum_1_2_3;
Out: 1 + 2 + 3;
```

Output can only return one Variable. A Vector can be used when multiple Variables need to be returned.

```php
Func: return_1_2_3;
Out: [1, 2, 3];
```

Multiple output Variables from a function can be assigned to one single Variable.

```php
Func: sum_1_2_3_vector;
In: a = return_1_2_3();
Out: a[0] + a[1] + a[2];
```

In this case, Variable `a` will become a Vector.

## Variable

Variables in Legit has three different Types, `NUMBER`, `STRING`, or `VECTOR`.

### Number:

```php
a = 0;                                  # a = 0
b = 1 + 2;                              # b = 3
c = 3.14159;                            # c = 3.14159
d = 99999999999999999;                  # d = 99999999999999999
```

In Legit, there is NO difference in Integer, Floating Number, or Long Number.

The precision of a Number is limited to `2^63`, roughly 17 digits.

### String:

```php
a = "this is a string";                 # a = "this is a string"
b = "another" + " " + "string";         # b = "another string"
c = a[0];                               # d = "t"
```

A String will always be inside a pair of double-quotes `""`.

Each character in a String is still considered to be a String. `[N]` can be used to indicate the `N+1`th element in the String, which is a String with only one character.

### Vector:

```php
a = [];                                 # a = []
b = [0, 1, 2];                          # b = [0, 1, 2]
c = ["0", "1", "2"];                    # c = ["0", "1", "2"]
d = [0, 1, 2, "0", "1", "2"];           # d = [0, 1, 2, "0", "1", "2"]
e = [[0, 1, 2], ["0", "1", "2"]];       # e = [[0, 2, 3], ["0", "1", "2"]]
```

Vector is an array of Variables, and can only be created using `[]`.

The Variables inside a Vector can be a Number, a String, or a Vector.

A Vector without any Variable can be defined with `[]`;

## Variable Operation

```php
In: a = 1, b = 2;
a = 3;                                  # a = 3
a = a + 1;                              # a = 4
a = b;                                  # a = 2
b = a;                                  # b = 2
```

Operations will be run through one by one in Top-Down order.

In a line of Variable Operation expression, there can only contain one value assignment `=`.

Operations that will generate each data type will be listed below.

### Number:

`+` will add the two Numbers. If the first Variable is a Number and the second Variable is NOT, the compiler will throw an error.

```php
In: a = 1, b = 1;
Out: a + b;                             # Out: 2
```

`-` will minus the first Number by the second Number.

```php
In: a = 2, b = 1;
Out: a - b;                             # Out: 1
```

`*` will multiply the two Numbers.

```php
In: a = 2, b = 3;
Out: a * b;                             # Out: 6
```

`/` will divide the first Number by the second Number.

```php
In: a = 6, b = 2;
Out: a / b;                             # Out: 3
```

`%` will calculate the remainder after dividing the first Number by the second Number.

```php
In: a = 5, b = 3;
Out: a % b;                             # Out: 2
```

`^` will time the first Number by the power of the second Number.

```php
In: a = 2, b = 3;
Out: a ^ b;                             # Out: 8
```

`num()` function can be used to parse a String into a Number-type Variable.

```php
Out: num("12345");                      # Out: 12345
```

`size()` function can calculate the length of a Vector.

```php
Out: size([1, 1, 1, 1, 1]);             # Out: 5
```

### String:

`+` will add two Strings together into one String. If the first Variable is a String and the second Variable is NOT, the compiler will throw an error.

```php
In: a = "this is ", b = "legit";
Out: a + b;                             # Out: "this is legit"
```

The index of String starts from `0`.

`[N]` can indicate the `N+1`th element in the String.

```php
In: a = "01234";
Out: a[2];                              # Out: "2"
```

`str()` function can be used to transform a Variable into a String-type Variable.

```php
Out: str(12345);                        # Out: "12345"
```

`inverse()` will inverse the order of characters in a String from left to right.

```php
Out: inverse("legit");                  # Out: "tigel"
```

`takeLeft(, N)` will take the first `N` Numbers of characters.

```php
Out: takeLeft("legit", 3);              # Out: "leg"
```

`takeRight(, N)` will take the last `N` Numbers of characters.

```php
Out: takeRight("legit", 3);             # Out: "git"
```

`dropLeft(, N)` will drop the first `N` Numbers of characters.

```php
Out: dropLeft("legit", 3);              # Out: "it"
```

`dropRight(, N)` will drop the last `N` Numbers of characters.

```php
Out: dropRight("legit", 3);             # Out: "le"
```

### Vector:

If the first Variable is a Vector, `+` will push the second Variable into the Vector after the last element.

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

`++` can concatenate two Vectors. Binding the head of the second Vector to the tail of the first Vector.

```php
In: a = [0, 1], b = [2, 3];
Out: a ++ b;                            # Out: [0, 1, 2, 3]
```

The index of Vector starts from `0`.

`[N]` can indicate the `N+1`th element in the Vector.

```php
In: a = [0, 1, 2, 3];
Out: a[2];                              # Out: 2
```

Unlike String, elements getting from Vector will NOT necessarily be a Vector.

`inverse()` will inverse the order of the elements in the Vector from left to right.

```php
Out: inverse([0, 1, 2, 3]);             # Out: [3, 2, 1, 0]
```

`takeLeft(, N)` will take the first `N` Numbers of elements.

```php
Out: takeLeft([0, 1, 2, 3], 3);         # Out: [0, 1, 2]
```

`takeRight(, N)` will take the last `N` Numbers of elements.

```php
Out: takeRight([0, 1, 2, 3], 3);        # Out: [1, 2, 3]
```

`dropLeft(, N)` will drop the first `N` Numbers of elements.

```php
Out: dropLeft([0, 1, 2, 3], 3);         # Out: [3]
```

`dropRight(, N)` will drop the last `N` Numbers of elements.

```php
Out: dropRight([0, 1, 2, 3], 3);        # Out: [0]
```

## Condition

Conditions in Legit only exit in two kinds of statements, `if` and `while`.

Each condition statement will have a Decision and some Variable Operations.

```php
In: a = 0, b = 1;
if a > b: a = a + 1, b = b + 1;         # two variable operations
Out: a + b;                             # Out: 1
```

While we all love `switch` or `match`, it is NOT that readable in small screen since it natively contains a hierarchical structure.

Also, there is NO `for` loop in Legit. Since `for` loop will often need to define another Variable as the index or element in a Vector, it is against the designing philosophy of Legit.

### Relational Operator:

`==` check if the first Variable is identical to the second Variable.

```php
In: a = 0;
if 1 == 2: a = 1;
Out: a;                                 # Out: 0
```

`!=` check if the first Variable is NOT identical to the second Variable.

```php
In: a = 0;
if 1 != 2: a = 1;
Out: a;                                 # Out: 1
```

`>` check if the first Number is bigger than the second Number.

```php
In: a = 0;
if 1 > 2: a = 1;
Out: a;                                 # Out: 0
```

`<` check if the first Number is smaller than the second Number.

```php
In: a = 0;
if 1 < 2: a = 1;
Out: a;                                 # Out: 1
```

`>=` check if the first Number is bigger than or equal to the second Number.

```php
In: a = 0, b = 0;
if 1 >= 2: a = 1;
if 1 >= 1: b = 1;
Out: [a, b];                            # Out: [0, 1]
```

`<=` check if the first Number is smaller than or equal to the second Number.

```php
In: a = 0, b = 0;
if 1 <= 2: a = 1;
if 1 <= 1: b = 1;
Out: [a, b];                            # Out: [1, 1]
```

### Logical Operator:

In condition operation, `&` is used as `AND` while `|` is used as `OR`.

Since `true` or `false` is NOT a type of Variables, logical operators can only exist in `if` or `while`.

```php
In: a = 0, b = 0;
if 1 > 2 & 2 > 1: a = 1;                # false and true => false
if 1 > 2 | 2 > 1: b = 1;                # false or true => true
Out: [a, b];                            # Out: [0, 1]
```

To combine all these logical operators, one can use `()` to declare the calculation priority.

```php
In: a = 1, b = 2;
if (a > 1 & b > 1) | (a < 2 & b < 2): a = a + 1;
Out: a;                                 # Out: 1
```

The condition will be calculated as `(false and true) or (true and false)` => `false or false` => `false`.

### If, Else:

`If` contains one Decision and some Variable Operations.

`:` is used to separate Decision and Variable Operations.

Variable Operations are separated by `,`.

```php
In: a = 1, b = 1;
if a > 0: a = a + 1, b = b + 2;
Out: [a, b];                            # Out: [2, 3]
```

`if` condition can exist alone, but `else` condition always come with an `if`.

```php
In: a = 1, b = 1;
if a > 1: a = a + 1, b = b + 2;
else: a = a + 2, b = b + 1;
Out: [a, b];                            # Out: [3, 2]
```

In this case, Legit will NOT execute the second Variable operation `a = a + 1;`, and will execute the third Variable operation `a = a + 2;` instead.

### While:

In Legit, while is the only loop function.

`while` contains one Decision and some Variable Operations.

`:` is used to separate Decision and Variable Operations.

Variable Operations are separated by `,`.

Legit will keep running the Variable Operations when the Decision is true.

```php
In: a = 1;
while a < 3: a = a * 2;
Out: a;                                 # Out: 4
```

The Variable Operation `a = a + 2` will be executed for two times until `a` becomes `4` and is higher than `3`.

Here is an example of defining a function, to sum the Number in a Vector up.

```php
Func: array_sum;
In: a = [], b = 0, c = 0;
while b < size(a): c = c + a[b], b = b + 1;
Out: c;
```

With the function `array_sum` been defined, `array_sum([0, 1, 2])` will return `3`.
