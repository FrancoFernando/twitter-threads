https://twitter.com/Franc0Fernand0/status/1461655763277991936?s=20&t=kObvIjelj9qDiu4mJE-FGg

Many people are familiar with the asymptotic analysis of an algorithm.

But not everyone know about AMORTIZED asymptotic analysis.

If you want to understand:

👉 WHAT amortized analysis is
👉 WHY it is important
👉 WHEN you should use it

Keep reading this thread. Amortised complexity of an algorithm is defined as its average complexity over a large number of executions.

But what does this exactly mean?

Let's suppose the algorithm runs fast in most of the cases, but slow in a very few ones. The normal asymptotic analysis mainly considers the slow cases, putting an upper bound on the performances of the algorithm.

Instead, the amortized asymptotic analysis takes into account also that the fast and slow cases occur with a different frequency. Considering these frequencies, the amortized asymptotic analysis defines the average performance of the algorithm over a large number of executions.

This makes sense if you run the algorithm many times and you care the whole set of runs to be efficient and not a particular run. An example will make everything clear.

Let's consider the dynamic array data structure.

When the dynamic array becomes full, it creates a new array with the doubled size of the old array and copies all the items in the old array to the new array. This means that the insert operation in a dynamic array has 2️⃣ different time complexities:

▶️ O(1) for most of the cases
▶️ O(n) for the few cases when the array becomes full

where n is the array capacity. The amortized analysis comes in handy to express these 2 different time complexites.

How ?

Describing that once the worst case happened, it won’t happen again for so long that its cost is amortized. In the case of the dynamic array insertion, the worst case happen again only after n/2 items have been added since the previous worst case.

So adding n items really only takes O(1) because the cost of O(n) is amortized over n/2 insertions.

Other examples coming to my mind are:

- hash tables for which the O(1) look up is amortized
- disjoint sets for which the O(N) with path compression and weighted union is amortized

But of course the dynamic array is easier to understand.
