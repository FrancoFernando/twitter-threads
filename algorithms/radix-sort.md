https://twitter.com/Franc0Fernand0/status/1456609174247415813?s=20&t=kObvIjelj9qDiu4mJE-FGg

🔑 Algorithm Explained 🔑

Radix Sort is an advanced and unique sorting algorithm.

📌 It works well for sorting integer values.

📌 It's based on the principle that numbers are made of digits.

How to implement it step by step ?

A thread.



Radix Sort sorts the input numbers looking at one digit at time, starting from the least significant one.

First using the units columm, then the hundreds column, the thousands column and so on.

Here is what happen during the different steps.



Let's see the steps to implement the algorithm, supposing all integers are positives.

1️⃣ Finding the maximum element and count its digits.

The maximum number of digits of a number corresponds to the number of iterations of the algorithm. 2️⃣ Iterate through each digit starting from the least significant one.

3️⃣ Arrange the numbers on the basis of the current digit.

4️⃣ Return the sorted output

The step number 3 is the most important.

You need an algorithm able to sort your numbers efficiently based on the current digit.

The algorithm shall also be stable, preserving the existing order between numbers having the same digit.

Which algorithm would you choose? There are many possibilities, but the best answer is Counting Sort.

Why?

Because the algorithm is stable and there is a clear upper bound on the possible number of digits.

If you're not familiar with counting sort you can check this thread 👇


Asymptotic analysis.

Time complexity is O(d * n), where d is the maximum number of digits and n is the size of the input array.

The Counting Sort is executed d times and it takes O(n).

Space complexity is O(n) because counting sort requires a temporary array to sort. Special cases.

Negative integers can be easily handled considering the sign as an additional digits.

Radix sort is also well suited for sorting strings in lexicographic order. C++ Implementation



Python Implementation



C# Implementation

