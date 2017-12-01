![alt tag](./asset/legit_banner.png)

a simple language to learn to programme

## Legit as a Programming Language:

Legit is designed to be a simple programming language for people to learn the concept of programming.

By restricting the use of local variables and forced each logical segment to be modulized into a small Function, each Function will only contain very simple logic.

With the code torn down, Legit can be read and write with ease even with a small screen in the era of the mobile phone.

The coding style of Legit is highly similar to Python.

In fact, Legit can be executed with any Python compiler, making it easy for people to catch up and run the code wherever they want.

## Examples

Before explaining the details, here are some examples.

### Example 1: Function Name, Input, Output

```python
def ex1(a):                             # input variable a
    return a                            # output variable a
```

### Example 2: Default Value, Variable Operation

```python
def ex2(a = 1):                         # default a be 1 if no input value is assigned
    a = a + 2                           # math operation expression
    return a                            # output variable a
```

### Example 3: If, Else, While Loop

```python
def ex3(a):
    if a > 2: a = a + 3                 # if a is bigger than 2
    else: a = a + 1                     # if a is not bigger than 2
    while a < 3: a = a + 1              # a keeps adding 1 while a is smaller than 3
    return a
```

### Example 4: Multiple Input Variables, Vector Output

```python
def ex4(a, b):                          # initiate 2 variables
    while a < 3: a = a + 1; b = b - 1   # 2 operations in 1 condition
    return [a, b]                       # vector output
```

### Example 5: No Input, Calling Another Function

```python
def ex5():
    return ex2()                        # output = 3
```

## Comment

In a line of Legit, everything after `#` does NOT count.

```python
def test_function(a = 1):               # this does not count
    a = a + 1                           # bla bla bla
    return a                            # still does not count
```

## Function Name

The name of the Function is defined after `def`.

```python
def function_name():
```

In this case, the name of the Function is `function_name`.

Function names can only contain words, numbers and `_`.

Chars such as `SPACE` and `+-*/\|'"~!@#$%^&()[]{}<>?:;.,` are NOT allowed as the name of a Function.

## Input and Output

### Input:

In input declaration, multiple Variables can be defined and all Variables must be defined with the function.

Programmers will need to create a new Function to separate local Variables.

A default value can be assigned to a Variable while initiating.

```python
def test(a = 0, b = 0):
    return a * 3 + b * 2
```

In this case, `test()` is `0`, `test(1)` is `3`, and `test(1, 1)` is `5`.

Variables will be taken in one by one and can NOT be assigned in another order.

Variable names can only contain words, numbers and `_`.

Chars such as `SPACE` and `+-*/\|'"~!@#$%^&()[]{}<>?:;.,` are NOT allowed as the name of a Variable.

If the Function does NOT need any Variable, the Function can still be declared with a `()`.

```python
def return_1():
    return 1
```

Whether the Function has an input Variable or NOT, a Function should always be called with a `()`.

```python
a = return_1()
```

### Output:

An Output is necessary for a Legit Function.

A Function always needs to return something.

Output can return a mathematical operation of some Variables.

```python
def sum_1_2_3():
    return 1 + 2 + 3
```

Output can only return one Variable. A Vector can be used when multiple Variables need to be returned.

```python
def return_1_2_3():
    return [1, 2, 3]
```

Multiple output Variables from a Function can be assigned to one single Variable.

```python
def sum_1_2_3_vector(a = return_1_2_3()):
    return a[0] + a[1] + a[2]
```

In this case, Variable `a` becomes a Vector.

## Variable

Variables in Legit has three different Types, `NUMBER`, `STRING`, or `VECTOR`.

### Number:

```python
a = 0                                   # a = 0.0
b = 1 + 2                               # b = 3.0
c = 3.14159                             # c = 3.14159
d = 99999999999999999                   # d = 1e+17
```

In Legit, all numbers are taken as Floating Number for simplicity.

The precision of a Number is limited to 15 digits.

### String:

```python
a = 'this is a string'                  # a = 'this is a string'
b = 'another' + ' ' + 'string'          # b = 'another string'
c = a[0]                                # d = 't'
```

A String will always be inside a pair of quotes `''`.

Each character in a String is still considered to be a String. `[N]` can be used to indicate the `N+1`th element in the String, which is a String with only one character.

### Vector:

```python
a = []                                  # a = []
b = [0, 1, 2]                           # b = [0, 1, 2]
c = ['0', '1', '2']                     # c = ['0', '1', '2']
d = [0, 1, 2, '0', '1', '2']            # d = [0, 1, 2, '0', '1', '2']
e = [[0, 1, 2], ['0', '1', '2']]        # e = [[0, 2, 3], ['0', '1', '2']]
```

Vector is an array of Variables, and can only be created using `[]`.

The Variables inside a Vector can be a Number, a String, or a Vector.

A Vector without any Variable can be defined with `[]`.

## Variable Operation

```python
def test(a = 1, b = 2):
    a = 3                               # a = 3
    a = a + 1                           # a = 4
    a = b                               # a = 2
    b = a                               # b = 2
    return [a, b]
```

Operations will be run through one by one in Top-Down order.

In a line of Variable Operation expression, there can only contain one value assignment `=`.

Operations that will generate each data type will be listed below.

### Number:

`+` will add the two Numbers. If the first Variable is a Number and the second Variable is NOT, the compiler will throw an error.

```python
def test(a = 1, b = 1):
    return a + b
```

`-` will minus the first Number by the second Number.

```python
def test(a = 2, b = 1):
    return a - b
```

`*` will multiply the two Numbers.

```python
def test(a = 2, b = 3):
    return a * b
```

`/` will divide the first Number by the second Number.

```python
def test(a = 6, b = 2):
    return a / b
```

`%` will calculate the remainder after dividing the first Number by the second Number.

```python
def test(a = 5, b = 3):
    return a % b
```

`float()` Function can be used to parse a String into a Number-type Variable.

```python
float('12345')
```

`len()` Function can calculate the length of a String or a Vector.

```python
len('Legit')
```

```python
len([1, 3, 9, 1, 7])
```

### String:

`+` will add two Strings together into one String. If the first Variable is a String and the second Variable is NOT, the compiler will throw an error.

```python
def test(a = 'this is ', b = 'Legit'):
    return a + b
```

The index of String starts from `0`.

`[N]` can indicate the `N+1`th element in the String.

```python
def test(a = '01234'):
    return a[2]
```

`str()` Function can be used to transform a Variable into a String-type Variable.

```python
str(12345)
```

### Vector:

If the first Variable is a Vector, `+` will concatenate two Vectors. Binding the head of the second Vector to the tail of the first Vector. If the second Variable is NOT a Vector, the compiler will throw an error.

```python
def test(a = [0, 1], b = [2, 3]):
    return a + b
```

```python
def test(a = [0, 1], b = 2):
    return a + [b]
```

```python
def test(a = [0, 1], b = '2'):
    return a + [b]
```

The index of Vector starts from `0`.

`[N]` can indicate the `N+1`th element in the Vector.

```python
def test(a = [0, 1, 2, 3]):
    return a[2]
```

Unlike String, elements getting from Vector will NOT necessarily be a Vector.

## Condition

Conditions in Legit only exit in two kinds of statements, `if` and `while`.

Each condition statement will have a Decision and some Variable Operations.

```python
def test(a = 0, b = 1):
    if a > b: a = a + 1; b = b + 1      # two variable operations
    return a + b
```

While we all love `switch` or `match`, it is NOT that readable in small screen since it natively contains a hierarchical structure.

Also, there is NO `for` loop in Legit. Since `for` loop will often need to define another Variable as the index or element in a Vector, it is against the designing philosophy of Legit.

### Relational Operator:

`==` check if the first Variable is identical to the second Variable.

```python
def test(a = 0):
    if 1 == 2: a = 1
    return a
```

`!=` check if the first Variable is NOT identical to the second Variable.

```python
def test(a = 0):
    if 1 != 2: a = 1
    return a
```

`>` check if the first Number is bigger than the second Number.

```python
def test(a = 0):
    if 1 > 2: a = 1
    return a
```

`<` check if the first Number is smaller than the second Number.

```python
def test(a = 0):
    if 1 < 2: a = 1
    return a
```

`>=` check if the first Number is bigger than or equal to the second Number.

```python
def test(a = 0, b = 0):
    if 1 >= 2: a = 1
    if 1 >= 1: b = 1
    return [a, b]
```

`<=` check if the first Number is smaller than or equal to the second Number.

```python
def test(a = 0, b = 0):
    if 1 <= 2: a = 1
    if 1 <= 1: b = 1
    return [a, b]
```

### Logical Operator:

In condition operation, `&` is used as `AND` while `|` is used as `OR`.

Since `true` or `false` is NOT a type of Variables, logical operators can only exist in `if` or `while`.

```python
def test(a = 0, b = 0):
    if 1 > 2 & 2 > 1: a = 1             # false and true => false
    if 1 > 2 | 2 > 1: b = 1             # false or true => true
    return [a, b]
```

To combine all these logical operators, one can use `()` to declare the calculation priority.

```python
def test(a = 1, b = 2):
    if (a > 1 & b > 1) | (a < 2 & b < 2): a = a + 1
    return a
```

The condition will be calculated as `(false and true) or (true and false)` => `false or false` => `false`.

### If, Else:

`If` contains one Decision and some Variable Operations.

`:` is used to separate Decision and Variable Operations.

Variable Operations are separated by `;`.

```python
def test(a = 1, b = 1):
    if a > 0: a = a + 1; b = b + 2
    return [a, b]
```

`if` condition can exist alone, but `else` condition always come with an `if`.

```python
def test(a = 1, b = 1):
    if a > 1: a = a + 1; b = b + 2
    else: a = a + 2; b = b + 1
    return [a, b]
```

In this case, Legit will NOT execute the second Variable operation `a = a + 1` and will execute the third Variable operation `a = a + 2` instead.

### While:

In Legit, while is the only loop Function.

`while` contains one Decision and some Variable Operations.

`:` is used to separate Decision and Variable Operations.

Variable Operations are separated by `;`.

Legit will keep running the Variable Operations when the Decision is true.

```python
def test(a = 1):
    while a < 3: a = a * 2
    return a
```

The Variable Operation `a = a * 2` will be executed for two times until `a` becomes `4` and is higher than `3`.

Lots of operations can be implemented with while loop, the following are some examples.

#### Sum the Number in a Vector

```python
def vector_sum(a = [], b = 0, c = 0):
    while b < size(a): c = c + a[b]; b = b + 1
    return c
```

With the Function `vector_sum` been defined, `vector_sum([0, 1, 2])` will return `3`.

#### Inverse a String

```python
def inverse_str(s = '', o = '', i = 0):
    while i < size(s): i = i + 1; o = o + s[size(s) - i]
    return o
```

`inverse_str('hello')` will return `'olleh'`.