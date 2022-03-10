https://twitter.com/Franc0Fernand0/status/1473988209474424832?s=20&t=wUtTLoeMZXaddLg-JvLeNw

I often develop prototyping code and I usually find hard to use a TDD approach.

Why ?

1. I don't know the final result of my code
2. I always experiment & change specifications

But I still force myself to write tests.

How ?

With Test-Driven Bugfixing (TDB).

// THREAD // 🧵

This is my approach:

1. I find a bug
2. I write a test replicating the bug
3. I run the test and I check that it fails as expected
4. I fix the bug.
5. I run the test and check that it passes

Point 2 is crucial.

You need to force yourself writing the test before even trying to fix the bug.

Even if the bugfix is 2 lines of code and the writing the test takes 200 lines. But I find the effort of creating and maintaining these tests more than acceptable:

1. The test will remain in my test suite to avoid regressions
2. The overall number of tests will increase
