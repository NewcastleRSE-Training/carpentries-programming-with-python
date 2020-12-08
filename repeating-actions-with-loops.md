
## Repeating Actions with Loops


![loops image](img/loops_image.png)


## Exercises

### From 1 to N

Python has a built-in function called range that generates a sequence of numbers. range can accept 1, 2, or 3 parameters.

+ If one parameter is given, range generates a sequence of that length, starting at zero and incrementing by 1. For example, range(3) produces the numbers 0, 1, 2.
+ If two parameters are given, range starts at the first and ends just before the second, incrementing by one. For example, range(2, 5) produces 2, 3, 4.
+ If range is given 3 parameters, it starts at the first one, ends just before the second one, and increments by the third one. For example, range(3, 10, 2) produces 3, 5, 7, 9.

Using range, write a loop that uses range to print the first 3 natural numbers:

<details>
<summary>Solution
</summary>

```
for number in range(1, 4):
    print(number)
```

</details>

### Understanding the loops

Given the following loop:

```
word = 'oxygen'
for char in word:
    print(char)
```

How many times is the body of the loop executed?

+ 3 times
+ 4 times
+ 5 times
+ 6 times


<details>
<summary>Solution
</summary>


The body of the loop is executed 6 times.

</details>

### Computing Powers With Loops

Exponentiation is built into Python:

```
print(% ** 3)
```

Output 125

Write a loop that calculates the same result as 5 ** 3 using multiplication (and without exponentiation).


<details>
<summary>Solution
</summary>

<pre>
result = 1
for number in range(0, 3):
    result = result * 5
print(result)
</pre>

</details>




