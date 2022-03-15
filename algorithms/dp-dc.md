https://twitter.com/Franc0Fernand0/status/1463813875535646721?s=20&t=kObvIjelj9qDiu4mJE-FGg

Divide and Conquer (D&C) and Dynamic Programming (DP) are 2️⃣ great algorithmic techniques.

Both divide a given problem into subproblems and solve the subproblems.

How do you choose which one to use for solving a given problem ❓

🧵 👇

To answer this question you need first to understand if the subproblems overlap or not.

If they don't overlap you should use Divide at Conquer.

If they overlap you should use Dynamic Programming. Let's consider a problem P broken down into 2 smaller subproblems S1 and S2.

With D&C you would:

▶️ solve S1 and S2 separately
▶️ combine their solutions in a certain way
▶️ get the answer to P

A classic example is mergesort where you sort an array by:

▶️ dividing it into 2 subarrays
▶️ sorting the 2 subarrays independently
▶️ merging the sorted subarrays to get the original one sorted

There is no inter-dependency between the 2 subarrays for finding the solution. With DP the first thing you need to realize is that S1 and S2 overlap.

What does it means ?

Basically that there is an inter-dependency between S1 and S2. Let's suppose that S2 depends on S1.

This means that S1 has to be solved before S2 can be solved.

That's exactly what DP does when implemented in bottom up way. How ?

▶️ solving S1 first and remembering the result.
▶️ solving S2 utilizing the remembered result for S1 (S2 depends on S1)
▶️ solving P using the solutions of S2 and S1.

All you need to do is start from bottom (S1) and move gradually (through S2) towards up (P). A classic example is the fibonacci sequence: f(n) = f(n-1) + f(n-2).

The solution for f(n-1) depends on the solution for f(n-2).

The DP solution:

▶️ solve the problem for the smaller number first
▶️ reuse this value to calculate the larger value
▶️ get the final value
