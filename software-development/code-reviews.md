
Software engineers engage in code reviews daily.

But most developers can’t recognize a bad code review process. Even when they're right in the middle of one.

Thread: 3 signs of bad code reviews, and how your team can ship faster. 

I recently went again through "Master the Code Review", a course by @curtiseinsmann

The course is really great and I got many useful insights from it.

Here I share my 6 main takeaways: ↓

--

1. Many signals allow to understand if a code review process is bad.

Most of them are objective like:

• there are many review cycles
• discussions between author and reviewers are too long

But some are subjective like:

• authors feel too anxious about receiving feedback

--

2. Code reviews work better when performed asynchronously.

This usually increases people's focus and productivity.

And having written comments forces clarity of thought.

But in some cases, a synchronous review is better like fragile changes to critical part of the system.

--

3. A code review process should fix clear expectation for authors and reviewers.

Authors should carefully prepare a description and choose reviewers familiar with the code.

Reviewers should show ownership and responsibility, being kind and thorough while writing the comments.

--

4. Code review descriptions are important but should be brief and concise.

They should specify both what the code is doing and why this is done in that way.

They should also include the reasons behind any trade-off and links to external resources when necessary.

--

5. Reviewers needs clearly to look for flaws inside the diff like missed edge cases or possible optimizations.

But they need also to look for flaws outside the diff like:

• side effects on other part of the system
• not backwards compatible changes
• partial refactoring

--

6. Writing effective comments requires an iterative process. 

First write comments as you go through the code to clarify your thoughts.

Then change and rewrite them while getting clear picture of the code.

--

7. Good code review comments should:

• address the code and not the author
• clearly indicate if a remark is not blocking
• give a reason why a change should be done
• give possible suggestions for solving a problem

--

8. Shipping code with few review cycles require writing better code.

There are 3 things to keep in mind for this:

• have an opinion about what’s a readable code
• be empathic, value the readers time more than yours
• be intentional, backing any line of code to your opinions
--
9. Michael Jordan is the best basketball player of all time.

This is not surpring

But what's surprising is that this can be related to how you can be successful in code reviews.
--

That's it for this thread, thanks to you for reading and to @curtiseinsmann for creating such grea course.

Clearly there is much more you can learn from the course and I strongly suggest checking it out to everybody.

And of course to follow him on Twitter
