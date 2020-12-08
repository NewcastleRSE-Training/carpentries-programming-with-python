
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

<pre>
for number in range(1, 4):
    print(number)
</pre>

</details>

### Understanding the loops

Given the following loop:

<pre>
word = 'oxygen'
for char in word:
    print(char)
</pre>

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


print(% ** 3)

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

### Reverse a String

Knowing that two strings can be concatenated using the + operator, write a loop that takes a string and produces a new string with the characters in reverse order, so 'Newton' becomes 'notweN'.


<details>
<summary>Solution
</summary>

<pre>
newstring = ''
oldstring = 'Newton'
for char in oldstring:
    newstring = char + newstring
print(newstring)
</pre>

</details>

### Computing the Value of a Polynomial

The built-in function *enumerate* takes a sequence (e.g. a list) and generates a new sequence of the same length. Each element of the new sequence is a pair composed of the index (0, 1, 2,…) and the value from the original sequence:


<pre>
for idx, val in enumerate(a_list):
    # Do something using idx and val
</pre>

The code above loops through a_list, assigning the index to idx and the value to val.

Suppose you have encoded a polynomial as a list of coefficients in the following way: the first element is the constant term, the second element is the coefficient of the linear term, the third is the coefficient of the quadratic term, etc.

<pre>
x = 5
coefs = [2, 4, 3]
y = coefs[0] * x**0 + coefs[1] * x**1 + coefs[2] * x**2
print(y)
</pre>

Output
<pre>
97
</pre>

<details>
<summary>Solution
</summary>

<pre>

y = 0
for idx, coef in enumerate(coefs):
    y = y + coef * x**idx
</pre>

</details>