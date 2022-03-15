https://twitter.com/Franc0Fernand0/status/1462424243455799297?s=20&t=kObvIjelj9qDiu4mJE-FGg

🔑Algorithm Explained 🔑

Divide et conquer is a powerful algorithmic technique.

How it works ?

🔸 divide a large problem into smaller ones
🔸 solve the smaller problems independently
🔸 combine the solutions of smaller problems into a solution for the large one

A thread.



Let's check how each step works considering a simple problem.

Let's suppose you want to find the maximum value of an array of integers.

How can you use a divide et conquer approach? 1️⃣ Divide the problem

You divide the input array into 2 subarrays: left and right

The problem is then divided in finding the maximum of both the left and the right subarray. 2️⃣ Conquer the subproblems

You find the maximum of the left and right subarrays by dividing them recursively.

When they are small enough (size == 1), you get the base case since the only element is the maximum. 3️⃣ Combine the solutions to the sub-problems into the solution for the original problem.

At each recursion step you get the maximum of the current array by taking the greater value between the maximum of the left subarray and the maximum of the right subarray. Find maximum with divide et conquer in Python 👇



Find maximum with divide et conquer in C++

