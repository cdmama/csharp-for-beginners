# Lesson 4: Operators

In the previous lesson, we mentioned that the type of a value can determine the _operations_ that can be performed with it.

For example, we can add two integers:

```csharp
10 + 2
```

The `+` symbol between the two numbers is an _operator_. It represents the regular ol' addition operator that is used in maths.

The whole line above is called an _expression_. Expressions can be evaluated further by C\# to produce a new value.

Type the line into your code box and run the program. You'll see that C\# evaluates the expression and displays the result.

{% hint style="danger" %}
Why did it display the result even if we didn't call `Console.WriteLine()`? 

Dotnet Interactive Notebook is also a [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) - an environment that allows quick evaluation of an expression, after which the output is displayed. 

If we write more than one statement in the code box, it won't be a single expression anymore and instead of doing the read-evaluate-print loop, Dotnet Interactive will compile the program as a whole.
{% endhint %}

We can also do subtraction, multiplication, and division - they each have their own operator.

```csharp
10 - 2    // subtraction
```

```csharp
10 * 2    // multiplication
```

```csharp
10 / 2    // division
```

Type each line above in the code box one at a time and run the program each time. The output will be the result of the arithmetic expression.

If you try to write all of them at the same time and run the program, you'll get an error. 

```csharp
10 + 2
10 - 2
10 * 2
10 / 2
```

Even if we put semicolons at the end of each line, the program will still be invalid!

That's because expressions are not valid statements. As we learned in Lesson 1, C\# programs are made of statements. Expressions in C\# programs must be used as part of a statement.

What's a statement we've already learned? Why, the **print** statement of course!

Wrap each expression into a `Console.WriteLine()` call.

```csharp
Console.WriteLine(10 + 2);
Console.WriteLine(10 - 2);
Console.WriteLine(10 * 2);
Console.WriteLine(10 / 2);
```

The result of each expression is now displayed.

