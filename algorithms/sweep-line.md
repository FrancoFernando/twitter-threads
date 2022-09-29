Sweep line is an algorithmic pattern that can be used to solve many coding problems.

The key idea is to process a set of events or points in a sorted order.

This is a simple example of how it works: ↓

{1/6}



Let's consider a shop and the arriving and leaving times of all the customers in a day.

Let's suppose that we need to calculate the maximum number of customers in the shop at the same time.

{2/6}

We can solve the problem creating 2 events for each customer: one for the arrival and one for the leaving.

After doing this, we can sort the events and map them on a line representing the time.

Then we process the events in order according to their times.

{3/6}

While going through the events, we can keep a counter.

The counter increases for each arrivals and decreases for each leaving.

The largest value of the counter gives the answer to the problem.

{4/6}

The sweep line part takes only O(n) time, but the overall algorithm takes O(nlogn) because of the sorting step.

This is anyway better than the brute force solution that would require to compare the events related to each pair of customers in O(N²)

{5/6}

This was just a simple example.

But actually the sweep line is a key technique in computational geometry and can solve complex problems like:

- find the closest pair of points in a set
- find the area of a union of rectangles
- find the convex hull of a set of points

{6/6}
