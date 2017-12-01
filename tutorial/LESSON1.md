## Tutorial - Lesson 1

Before we start playing around, let's take a look at some codes.

```python
def f(a = 1):
    a = a + 1       # 1 operation
    a = a * 2       # 2 operation
    return a

3 == f()            # Evaluation Value
```

In initialization `def f(a = 1):`, one Variable `a` is initialized with a default value `1`.

After the first operation `a = a + 1` is processed, `a` is assigned to `2`.

Then the second operation `a = a * 2` is processed and re-assign `a` to `4`.

Then the output line `return a` return the Number `4`.

Here, The evaluation value is `3` and is conflicted to the processed result `4`.

Therefore, the code is NOT Legit.

Now, let's swap the order of the operations in the code.

```python
def f(a = 1):
    a = a * 2       # 2 operation
    a = a + 1       # 1 operation
    return a

3 == f()            # Evaluation Value
```

After changing the order of the operations, `a` is still initialized as `1`.

Then `a = a * 2` will assign `a` to `2`.

And the next operation `a = a + 1` will re-assign `a` to `3`.

The evaluation value `3` matches the output result `3`

The code is Legit.