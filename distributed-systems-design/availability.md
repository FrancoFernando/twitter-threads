Availability is critical for distributed systems.

A downtime of 1 hour:

• costs from $1K to $1M.
• affect the system credibility
• decrease the customers trust

Here's how you can get a system available.

// THREAD //

🧵↓↓

1️⃣ Definition

Availability is a measure of how a system is resistent to failures.

The more a system stays operational when a component fails, the higher is its availability. 2️⃣ Measure

Availability is the percentage of time a system remains functional in a specific period.

Real systems needs to guarantee high level of availability with all nines in percentage. What does this mean in concrete ?

- 99% means 88 hours of downtime per year

- 99.9% means 9 hours of downtime per year

- 99.99% means 53 minutes of downtime per year

- 99.999% means 6 minutes of downtime per year

Examples of system requiring 5 nines of availability are :

- financial services
- hospitals data centers
- cloud providers like AWS
- safety critical systems (i.e. airplanes)

3️⃣ KPIs

Many systems offer explicit guarantees of availability:

- SLA (Service Level Agrement) ➔ a contract between a service provider and its end users made by multiple SLOs

- SLO (Service Level Objective) ➔ a specific agreement between a service provider and its end users

Some examples of SLOs are:

- the system will be available 99.95% of the time
- the system will reply within 3 seconds to 99% of requests

Service Level Indicators (SLIs) are the metrics used to verify if the agreements defined by SLOs are satisfied. 4️⃣ Design

High availability always comes with trade offs and has an impact on the choices during system design.

For example, increasing availability can reduce the performances or the data consistency.

So it's important to understand which parts of a system are critical. For example, considering a shopping website:

- the payment subsystem shall be high available not to lose money and customers

- the dashboard monitoring the sales can have more relaxed availability requirements

5️⃣ Solutions

The key is avoiding that a failure of some parts makes the whole system going down.

How to avoid these single points of failures ?

Introducing redundancy and replicating critical parts of the system. The simple way to have redundancy is adding more components.

Everything can be replicated: servers, databases, load balancers and so on.

According to the replicas we can distinguish between passive and active redundancy. Passive redundancy is when all redundant components work.

When one component dies, all the others keep working.

Easier to implement than active redundancy. Active redundancy is when only one or some of the redundant components work.

When one component dies, the other somehow know, reconfigure themselves and start working.

This often requires a "leader election" mechanism to identify the component going to step up and work. Redundancy can't completely avoid failures and some failures needs to be handled by humans.

It is important to define strictly regulated processes to ensure that the failure will be handled in an acceptable timeframe.
