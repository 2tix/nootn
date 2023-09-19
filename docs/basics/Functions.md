# Functions
As I said in the [Types](Types.md) section, functions are a type of variable in Nootn, they are defined as follows:
```nootn
sum = (x, y) => { // If there is just one argument, you can omit the parentheses
    return x + y
}
```
You can also define types in a function definition:
```nootn
sum: function<int> = (x: int, y: int) | (x: float, y: float) => {
    return x + y
}
```
## Calling functions
Nootn functions can be read just like other variables, however, this will not run the function, it will just return the function itself. To run a function, you have to use the `()` operator:
```nootn
!sum // This will print the function itself
!sum(3, 4) // This will print 7
```
## Function mutability
Just like variables, functions can be mutable or immutable. To make a function immutable, you can use the `const` keyword:
```nootn
const sum = (x, y) => {
    return x + y
}
sum = (x, y) => {
    return x - y
} // This will cause an error
```
In the next tutorial, we will learn about loops and conditionals.
