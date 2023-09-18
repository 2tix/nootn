# Say hello, nootn!
Let's start with writing a simple program that prints "Hello world!" to the console.

```nootn
!"Hello world!"
```

This is the simplest program you can write in nootn. It consists of a single expression, which is a string literal. The `!` operator prints the value of the expression to the console.

### (Optional) The other way to do it
Although you can use the `!` operator to print a string, it is not the only option. You can also use the `print` function, which is a built-in function that prints its argument to the console. (the `!` operator is a limited version of the `print` function that only accepts a single argument)

```nootn
print("Hello world!")
```

## Running the program
There are two ways to run a nootn program. The first way is to use the `nootn` command-line tool. The second way is to use the nootn notebook (more on that later). For now, we will use the command-line tool. To run the program, save it to a file named `hello.nootn` and run the following command:

```bash
nootn hello.nootn
```

This will run the program and print the following output to the console:
```text
Hello world!
```
If you want the program to write the output in a file instead of printing it to the console, you can use the `-o` option:
```bash
nootn hello.nootn -o hello.txt
```

That's it for now. In the next tutorial, we will learn about variables.