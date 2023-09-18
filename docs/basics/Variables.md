# Variables
Like all programming languages, Nootn has variables. A variable is a name that refers to a value. You can think of a variable as a box that contains a value. You can put a value in the box, look at it, or replace it with a different value. Variables in Nootn are defined using the `=` operator. For example, the following program defines a variable named `a` and assigns it the value `3`:
```nootn
a = 3
```
You can then print the value of the variable using the `!` operator:
```nootn
!a
```
This will print the following output to the console:
```text
3
```
You can also define multiple variables in a single statement:
```nootn
a, b = 3, 4
```
We can perform math on variables wherever we want, this is done by using the `+`, `-`, `*`, `/`, `**`, and `%` operators or some in-built functions like `sqrt`:
```nootn
c = sqrt(a**2 + b**2)
!c
```
Here the `sqrt` function is used to calculate the square root of the sum of the squares of `a` and `b`. The `**` operator is used to calculate the power of a number. The `%` operator is used to calculate the remainder of a division. The following program calculates the remainder of dividing `a` by `b`:
```nootn
!a % b
```

## Mutability
If you define a variable with the `name = value` syntax you can always change its value later. However, if you want to make a variable immutable (i.e. you can't change its value later) you can use the `const name = value` syntax. For example, the following program defines an immutable variable named `A` (in Nootn the convention is to name constants in capital letters) and assigns it the value `3`:
```nootn
const A = 3
A = 4 # This will cause an error
```

In the next tutorial, we will learn all types of variables there are in Nootn.
