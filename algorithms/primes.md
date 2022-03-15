https://twitter.com/Franc0Fernand0/status/1446407960196964364?s=20&t=kObvIjelj9qDiu4mJE-FGg

A number is prime if it is divisible only by 1 and itself.

For example 2, 3 and 257 are all prime, while 15 is not prime because it is divisible by 3 and 5.

How can we efficiently check if a number is prime?

How can we calculate all prime numbers within a range?

A thread.



How can we check if a number is prime?

The easiest way to find if a number n is prime is checking if it is divisible by any of the numbers below it.

We can use the modulo operator (%) to check for divisibility.



The previous approach works, but it can be optimized.

A first small optimization is based on the fact that are no even primes greater than 2.

So if we first check that n is not even, we can increment the numbers below it by 2. A second optimization stops the increment to the square root of n.

Why is this possible?

If n was divisible by a number greater than m = sqrt(n), then the result of that division would be some number x < m.

But in that case we would have already found that number 😀



How we can calculate all prime numbers within a range?

The brute force solution to find all the primes from 1 to n would be to call the previously defined method n times.

This would be very inefficient since we would repeat the same calculations over and over again. A better approach is to use a method known as the Sieve of Eratosthenes.

The method begins by assuming that all numbers are prime.

It then takes the first prime number and removes all its multiples.

The same technique is then applied to the next prime number.

