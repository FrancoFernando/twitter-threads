https://twitter.com/Franc0Fernand0/status/1461655763277991936?s=20&t=kObvIjelj9qDiu4mJE-FGg

Amortized analysis is an alternative way to evaluate the performance of an algorithm.

How it differs from asymptotic analysis and when it's important: ↓  {1/9}

The amortised analysis of an algorithm measures its average complexity over a large number of executions.

Let's suppose that an algorithm runs fast in most of the cases, but slow in a very few ones.

{2/9}

The asymptotic analysis puts an upper bound on the performances of the algorithm considering the slow cases.

Instead, the amortized asymptotic analysis takes into account also that the fast and slow cases occur with a different frequency. 

{3/9}

It consides these frequencies to define the average performance of the algorithm over a large number of executions.

This makes sense if you run the algorithm many times and you care the whole set of runs to be efficient and not a particular run.

{4/9}

Let's clarify this with the help of the dynamic array data structure.

When a dynamic array becomes full, it creates a new array with a double capacity of the old array.

All the items in the old array are then copied to the new array.

{5/9}

This means that the insert operation in a dynamic array has 2 different time complexities:

• O(1) for most of the cases
• O(n) for the few cases when the array gets full

N here is the array capacity.

{6/9}

The amortized analysis comes in handy to express these 2 different time complexites.

It expresses the fact that once the worst case happens, it won’t happen again for so long that its cost is amortized.

{7/9}

In the case of the dynamic array insertion, the worst case happen again only after n/2 items have been added.

So using the amortized analysis, the insertion of n items takes O(1) because the worst case cost of O(n) is amortized over n/2 operations.

{8/9}

Dynamic arrays are a classical example where applying amortized analysis makes sense.

Other examples you can check are:

• hash tables with amortized O(1) look up 

• disjoint sets with amortized O(n) find and unite operations using path compression and weighted union

{9/9}
