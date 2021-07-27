# Lesson 3.5: Type Conversion

{% hint style="warning" %}
At the end of this lesson, you should be able to answer the following:

* What is implicit conversion?
* What is explicit conversion?
* How do I convert between types in C\#?
{% endhint %}

In [Lesson 3](../tutorial/lesson-3-data-types.md), we learned some of the data types that are available in C\#. 

We also learned from [Lesson 5](../tutorial/lesson-5-variables.md#assigning-to-variables) that once a variable has been declared with a type, the type cannot be changed. So a variable with a type of `double` can only hold `double` values. It can't hold a `string` or a `bool` value. But what about an `int`?

Let's test it out by declaring an `int` variable, then assigning it to a `double` variable.

```csharp
int myInt = 300;
double myDouble = myInt;
Console.WriteLine(myDouble);
```

Because both variables can hold numeric values, we are able to assign the `int` value into a `double` variable with no issues. 

This doesn't mean that `myDouble` has become an `int` type, or that it can hold `int` values. Rather, C\# automatically converted our `int` value into a `double` value. This is called _implicit conversion_.

What happens when we try to do the reverse? That is, assign a `double` value to an `int` variable.

```csharp
double myDouble = 5.5; // Remember that a double can have fractional parts (decimal point)
int myInt = myDouble;
Console.WriteLine(myInt);
```

It turns out that C\# will not even allow us to run the above code snippet. When we hover over the red squiggly part, C\# lets us know what the error is:

`Cannot implicitly convert type 'double' to 'int'. An explicit conversion exists (are you missing a cast?)`

This error means that C\# doesn't allow implicit conversions from a `double` to an `int`. Why is that?

Below are the maximum values for these two types. The `double` type can hold values significantly bigger than an `int`. 

* `int`: 2,147,483,647
* `double`: 1.7 × 10^308

When you try to assign a value of type `double` into an `int`, the value you are assigning can be potentially bigger than what the variable can hold, causing a loss of information. So C\# doesn't do the conversion automatically for us. Instead, we must make our intentions clear via an _explicit_ _conversion._

To let C\# know that we are okay with the conversion, we can cast our variable to the desired type. We specify the target type in round brackets before the variable or value.

Change Line 2 above to the following line:

```csharp
int myInt = (int) myDouble;
```

Now C\# will let us run the program. However, the value printed out is not `5.5`. Do you know why?

That's right - an `int` type can only hold integral values, so the fractional part \(`0.5`\) is lost upon conversion.

Explicit conversion only works for types that are compatible. Both `int` and `double` are numeric types, so we can use it.

### Helper methods

What about converting between types that are not compatible, such as a `string` and an `int`? Or a `bool` and a `double`? 

Fortunately, the C\# standard library has helper methods that can assist with conversion. They are all in the `Convert` class:

* `Convert.ToBoolean()` 
* `Convert.ToInt32()`
* `Convert.ToDouble()`
* `Convert.ToString()`

These methods take a value of any type and will try to convert it to the type specified in the method name. Of course, not all values can be converted. The input has to be in the correct format for the conversion to succeed.

```csharp
// This is okay
var aNumberString = "99.9";
var myDouble1 = Convert.ToDouble(aNumberString);

// This is not okay
var aTextString = "double trouble";
var myDouble2 = Convert.ToDouble(aTextString);
```

{% hint style="info" %}
**Question**

Why would we have a need to convert between types? Can you think of some situations where it would be practical?
{% endhint %}

{% hint style="info" %}
**Question**

In your own words, explain the difference between implicit and explicit conversion.
{% endhint %}

{% hint style="info" %}
**Challenge**

Explore the conversion helper methods over at [this page](https://docs.microsoft.com/en-us/dotnet/api/system.convert?view=net-5.0). See if you can make successful conversions between the different types.
{% endhint %}

