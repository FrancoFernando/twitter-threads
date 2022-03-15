https://twitter.com/Franc0Fernand0/status/1460884571055173633?s=20&t=kObvIjelj9qDiu4mJE-FGg

Tests make sure that changes to your code are working as expected.

But wait!

There are many kind of tests:

▶️ Unit
▶️ Integration
▶️ Functional
▶️ End-to-end
▶️ Acceptance
▶️ Performance
▶️ Smoke

Do you know how they differ and which you should use?

A thread 🧵 👇

1️⃣ Unit tests

▶️ are very low level, close to the source code

▶️ tests individual methods and functions of the classes or modules used by your software

▶️ are easy to automate and can be run very quickly by a continuous integration server

2️⃣ Integration tests

▶️ check that different modules or services used by your application work well together

▶️ i.e, they can test the interaction with the database

▶️ are more expensive since they require multiple parts of the application to be up and running. 3️⃣ Functional tests

▶️ focus on the business requirements of an application

▶️ only verify the output of an action without checking the intermediate states of the system

▶️ i.e, they can test if the application get a specific value from the database according to requirements

4️⃣ End-to-end tests

▶️ replicates a user behavior with the software in a complete application environment

▶️ verifies that various user flows work as expected

▶️ are expensive to perform and hard to maintain when automated

▶️ better having only a few key end-to-end tests

5️⃣ Acceptance tests

▶️ formal tests executed to verify if a system satisfies the business requirements

▶️ like end-to-end tests focus on replicating user behaviors

▶️ in addition measure also the performance of the system, rejecting changes if some goals are not met

6️⃣ Performance tests

▶️ non-functional tests checking the behaviors of the system under significant load

▶️ i.e., observe the response times when executing a high number of requests

▶️ are costly to implement and run, but useful to understand if new changes degrade the system

7️⃣ Smoke tests

▶️ quick to execute tests checking the basic functionality of the application

▶️ useful after a new build befrore running more expensive tests

▶️ useful after a deployment to check that if the application is running properly
