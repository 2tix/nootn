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
a = "Hello world!" // This will cause an error
```

## Finding the type of value

To find the type of value, you can use the `type` function. For example, the following program prints the type of the value `3` and the type of the value `"Hello world!"`:
```nootn
!type(3)
!type("Hello world!")
```
## Numbers
We have 3 basic types of numbers in Nootn: `int`, `float`, and `complex`. `int` is a whole number, `float` is a decimal number, and `complex` is a complex number. You can define a number like this:
```nootn
a: int = 3
b: float = 3.14
c: complex = 3, 4
```

Where `z: complex = n, m` (n and m both being `float`), defines the number `z` such that:
$$z \in \mathbb{C}$$
$$n, m \in \mathbb{R}$$ 
$$z = n + mi$$

You can of course perform math on numbers:
```nootn
a: int = 3
b: float = 3.14
c: complex = 3.0, 4.0
!a + b
!type(a + b)
!a * b
!type(a * b)
!a / b + c
!type(a / b + c)
```
Notice that the type of the result of the math operation is the type of the most precise number in the operation. For example, in the last operation, the type of the result is `complex` because `c` is a `complex` number.

## Strings
A string is a sequence of characters - a text. You can define it as follows:
```nootn
str: string = "Hello world!"
```
You can also define a string using single quotes:
```nootn
str: string = 'Hello world!'
```
The difference between the two is that you can use double quotes inside a string defined with single quotes and vice versa:
```nootn
str: string = "Hello 'world'!"
str = 'Hello "world"!'
```
You can also use special quotes to define a string that spans multiple lines:
```nootn
str: string = `Hello
World!`
```
This notation can also be used to plug-in values from the code (like variables) using the `${value}` syntax:
```nootn
a: int = 3
str: string = `Hello ${a} world!`
```

### Working with strings
#### Math
You can perform some operations on strings, for example, you can concatenate two strings using the `+` operator:
```nootn
str1: string = "Hello"
str2: string = " world!"
!str1 + str2
```
You can also "subtract" a string from another string using the `-` operator, this will find all the occurrences of the second string in the first string and remove them:
```nootn
str1: string = "Hello wogoodbyerld!"
str2: string = "goodbye"
!str1 - str2
```
You can also multiply a string by an integer, this will repeat the string the specified number of times:
```nootn
str: string = "Hello"
!str * 3
```
Now you can also divide a string by another string - this will tell you how many times the second string can be found in the first string:
```nootn
str1: string = "Hello world!"
str2: string = "l"
!str1 / str2
```
#### Length
You can find the length of a string using the `length` attribute of any string:
```nootn
str: string = "Hello world!"
!str.length
```
#### Indexing
You can access a specific character in a string using the `[]` operator:
```nootn
str: string = "Hello world!"
!str[0]
```
You can also use negative indices to access characters from the end of the string (the last character has an index of `-1`):
```nootn
str: string = "Hello world!"
!str[-1]
```
You can also use the `[a, b]` operator to get a substring (a being inclusive and b being exclusive):
```nootn
str: string = "Hello world!"
!str[6:11]
!str[:5]# If you omit a, it will be assumed to be 0
!str[6:]# If you omit b, it will be assumed to be the length of the string
```
## Booleans
A boolean is a value that can be either `true` or `false`. You can define it as follows:
```nootn
a: bool = true
b: bool = false
```
You can also use the `not()' function to reverse a boolean:
```nootn
!true.not()
!false.not()
```
The following values are converted to `false` (when passed as a value of a boolean) - `[0, "", [], {}, (), undefined, null]` (also any other empty n-dimensional arrays, e.g. `[[[], []]]`) and everything else is converted to `true`.

You can also use binary operators on booleans:
```nootn
!true && false // AND
!true || false // OR
!true ^^ false // XOR
```
## Arrays
An array is a collection of values. Unlike other languages Nootn takes arrays more mathematically and distinguishes between 1-dimensional arrays, 2-dimensional arrays, n-dimensional arrays. 
### Vectors
A vector is a 1-dimensional array. You can define it as follows:
```nootn
a: vector = [1, 2, 3]
```
You can access the i-th element of a vector using the `[]` operator:
```nootn
a: vector = [1, 2, 3]
!a[0]
a[1] = 4 // you can also assign to an element
!a
```
### Matrices
A matrix is a 2-dimensional array. You can define it as follows:
```nootn
a: matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]e
```
As a matrix is just a vector of vectors, you can access the element in y-th row and x-th column using the `[y][x]` operator:
```nootn
!a[0][2]
```
### Tensors
A tensor is an n-dimensional array. You can define it as follows:
```nootn
a: tensor = [[[1, 2, 3], [4, 5, 6], [7, 8, 9]], [[1, 2, 3], [4, 5, 6], [7, 8, 9]]]
```
Now unlike in a lot of languages, in Nootn all rows and any other n-dimensional levels must all have the same length (rows the same length, columns the same length, but can be different from the length of a row). This is because Nootn takes arrays more mathematically, therefore this is not allowed:
```nootn
a: matrix = [
    [1, 2, 3], 
    [4, 5, 6], 
    [7, 8] 
] // I mean, this is not a matrix, right?
```
## Objects
An object is a collection of key-value pairs. You can define it as follows:
```nootn
a: object = {
    "key 1": (3, 4),
    key: "value2" // Keys do not have to be strings if they are valid identifiers (i.e. they do not contain spaces or special characters)
}
```
Key is now an attribute of the object, so you can access it using the `.` operator:
```nootn
!a.key
a.anotherKey = 0 // You can also assign to an attribute
```
or the `[]` operator for keys that are not valid identifiers:
```nootn
!a["key 1"]
a["key 2"] = 0
```
You can also delete keys from an object using the `delete` function or create new keys just by assigning to them:
```nootn
a.delete("key 1") // Here, you have to denote every key as a string
a["key 3"] = 0
```

## Functions
Although functions are variables just as any other, they are so important that they deserve their own section. That's why we will learn about them in the next tutorial.

## Custom types
You can define your own types using the `type` keyword. For example, you can define a type `Point` as follows:
```nootn
type Point = {
    x: float,
    y: float 
}
```
Using the `|` operator, you can define a type that can be either of the specified types:
```nootn
type Point = {
    x: float,
    y: float 
} | {
    x: int,
    y: int

type SpecialPoint = {
    x: float | int,
    y: float | int
}

point: Point = {
    x: 3,
    y: 4
}

point = {
    x: 3.0,
    y: 4.0
}

point = {
    x: 3.0,
    y: 4
} // This will cause an error
```
Unlike variables, types are immutable, so you cannot change them after they are defined.