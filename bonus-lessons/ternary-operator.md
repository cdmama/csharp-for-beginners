# Ternary Operator

{% hint style="warning" %}
At the end of this lesson, you should be able to answer the following:

* What is the ternary operator?
* Where can I use the ternary operator?
* How do I use the ternary operator in an expression?
{% endhint %}

In [Lesson 7](../tutorial/lesson-7-conditionals.md), we learned about the if-else statement that lets us represent a branching path in our programs. In this lesson, we will learn another way to depict a conditional expression.

The _ternary operator_ `?:` is useful to make quick if-else conditions that evaluates to a result.

```csharp
var isFemale = true;
var evolvedForm = isFemale ? "Nidorina" : "Nidorino";
```

Line 2 is using a ternary operator expression, in conjunction with a variable declaration. We have declared a variable named `evolvedForm`. Can you guess what type this variable will be?

`evolvedForm` is a string variable. The inferred value comes from the result of the ternary operator expression. Let's break it down:

* First is `isFemale`, followed by a `?`. The part that comes **before** the `?` is the condition. `isFemale` is a boolean variable declared in Line 1, with the value of `true`. 
* Next is a string value, `Nidorina`, followed by a `:`. The part that comes **before** the `:` is the result of the whole expression when the condition is `true`.
* Finally we have the string value `Nidorino` after the `:`. The part that comes **after** the `:` is the else clause or alternate path - the result of the expression when the condition is `false`.

In short, the syntax of the ternary operator expression is:

```text
<condition> ? <result-if-true> : <result-if-false>
```

Run the code and add a `Console.WriteLine(evolvedForm);` statement to display the result. Can you guess what the value of `evolvedForm` will be? How about if `isFemale` is set to `false`?

Here's what our code will look like as a regular if-else statement.

```csharp
var isFemale = true;

string evolvedForm;
if (isFemale) 
{
    evolvedForm = "Nidorina";
}
else
{
    evolvedForm = "Nidorino";
}
```

As we can see, using the ternary operator makes for more concise code!

Just like a regular if-else statement, the condition part of the ternary operator \(the part before the `?`\) can have more complex conditional expressions, like `age > 20`.

We can even chain ternary expressions. Use this sparingly, however - it can affect the readability of our code. Below, the result of the first ternary expression has been indented so it's easier to read the code.

```csharp
var isFemale = false;
var finalEvolution = true;

var evolvedForm = isFemale ? 
        finalEvolution ? "Nidoqueen" : "Nidorina" :
        finalEvolution ? "Nidoking" : "Nidorino";
        
Console.WriteLine(evolvedForm);
```

