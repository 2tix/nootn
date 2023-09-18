# Types

## Introduction

In this tutorial, we will learn about the different types of variables in Nootn. I previously mentoined that variables are like boxes that contain values. In most programming languages when we say type we mean the type of the box, for example in C++, if you define an `int` (whole number) like this:
```cpp
int a = 3;
```
you can then only assign whole numbers to `a` and not any other type of value. In Nootn, however, the type of the box is not important, what is important is the type of the value inside the box. For example, the following program is perfectly valid:
```nootn
a = 3
a = "Hello world!"
```

However, if you want a variable to only contain a specific type of value, you can achieve it like this:
```nootn
a: int = 3
a = "Hello world!" # This will cause an error
```
## Numbers
We have 3 basic types of numbers in Nootn: `int`, `float`, and `complex`. `int` is a whole number, `float` is a decimal number, and `complex` is a complex number. You can define a number like this:
```nootn
a: int = 3
b: float = 3.14
c: complex = 3, 4
```

<script type="text/javascript" async
    src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

Where `c: complex = n, m` defines the number $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

```nootn
