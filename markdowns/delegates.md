# Background: Delegates

Delegates are a very important part of LINQ. Much of the more powerful capabilities of LINQ make use of delegates.

A delegate is simply a reference to a method. Delegates can be stored and passed around in a variable, like so:


```C#
public delegate int FuncTwoInts(int, int);

public static void PrintWith_2and4(FuncTwoInts func)
{
    Console.WriteLine(func(2, 4));
}

public static void Execute()
{
    // Prints 8
    PrintWith_2and4((a, b) => a * b);
    // Prints 6
    PrintWith_2and4((a, b) => a + b);
    // Prints 224
    PrintWith_2and4((a, b) => int.Parse($"{a}{a}{b}"));
    // Prints 9999
    PrintWith_2and4((a, b) => 9999);
}
```

The method `PrintWith_2and4()` takes a delegate as a parameter. The passed-in delegate must accept two `int` parameters and return an `int`.