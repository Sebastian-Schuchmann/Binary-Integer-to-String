# Binary-Integer-to-String
Converting an int to a binary string in C#.

If you want to print your integers as Binary this function will help you do this! Works for negative numbers as well.

Don't forget to leave a ⭐️!

```c#
static string BinaryAsString(int num)
{
    int n = num;
    Stack<char> charStack = new Stack<char>();
    StringBuilder numString = new StringBuilder();

    if (num < 0) //Negative Numbers are stored as compliment
        n = (~n) + 1;
    
    while(n >= 1)
    {
        if ((n & 1) == 1)
            charStack.Push('1');
        else charStack.Push('0');
        
        n = n >> 1;
    }

    if (num == 0)
        charStack.Push('0');
     
    int characterCount = charStack.Count;
    for (int i = 0; i < characterCount; i++)
        numString.Append(charStack.Pop());
    
    return numString.ToString();
}
```
