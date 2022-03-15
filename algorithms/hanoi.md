https://twitter.com/Franc0Fernand0/status/1464954931278983180?s=20&t=kObvIjelj9qDiu4mJE-FGg

Algorithm explained: Tower of Hanoi 🔑

Tower of Hanoi is a famous mathematical puzzle.

Why is it popular ❓

Because it shows how powerful recursion can be when applied to algorithms definition.

Are you curious to learn more ❓

Keep reading this thread.



1️⃣ Problem definition

The puzzle consists of

🔸 3 pegs named A, B and C
🔸 n disks of different sizes named {1,...,n}

where 1 is the smaller disk and n the bigger one. At the beginning, all the disks are on peg A, in order of decreasing size from bottom to top.

The goal is to move all the disks from peg A to peg B following 2 rules:

🔸 you can move only one 1 disk at a time
🔸 you can never put a disk on top of a smaller disk

2️⃣ Base cases solution

When a problem looks difficult, it is always better to start with a simple scenario.

Let's consider the case with only 1 disk.

That's easy right?

You can always move the disk from A to B according to the rules.

How about 2 disks? You can solve it in 3 steps:

🔸 move disk 1 from A to C
🔸 move disk 2 from A to B
🔸 move disk 3 from C to B

Ok and now what about 3 disks? We already know how to move 2 disks. So we can:

🔸 move the tower of 2 disks 1,2 to peg C
🔸 move disk 3 to peg B
🔸 move the tower of 2 disks 1,2 to peg B

Do you start to see how recursion comes into play? 3️⃣ Recursive formulation

Our analysis gave us the steps to follow:

▶️ move a tower of height-1 to an intermediate peg, using the final peg
▶️ move the bottom disk to the final peg
▶️ move the tower of height-1 from the intermediate peg to the final peg using the original peg

Step 1. and 3. are the same instance of the original problem.

So they can be solved recursively until we hit the base case of a tower with only 1 disk

4️⃣ Implementation

Here you can find an implementation of the algorithm in different languages.

To facilitate your understanding I implemented an OOP version of the algorithm based on a Peg class. Tower of Hanoi: C++ Implementation 👇



Tower of Hanoi: Python implementation 👇



5️⃣ Asymptotic Analysis

The time complexity of the algorithm is exponential O(2^n) where n is the number of disks.

Why?

Each step of the algorithm executes 2 recursive calls decreasing the number of remaining disks by 1. Since the branching factor is 2 and the maximum depth of the recursion is n, the complexity is O(2^n).

The space complexity is instead O(n) because we need to store a maximum of n function calls on the stack frame.
