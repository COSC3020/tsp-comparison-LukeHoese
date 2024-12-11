# Traveling Salesperson Problem -- Empirical Analysis

For this exercise, you'll need to take the code from the TSP Held-Karp and TSP
Local Search exercises. This can be your own implementation or somebody else's.
You will now do an empirical analysis of the implementations, comparing their
performance. Both the Held-Karp and the Local Search algorithms solve the same
problem, but they do so in completely different ways. This results in different
solutions, and in different times required to get to the solution.

Investigate the implementations' empirical time complexity, i.e. how the runtime
increases as the input size increases. *Measure* this time by running the code
instead of reasoning from the asymptotic complexity (this is the empirical
part). Create inputs of different sizes and plot how the runtime scales (input
size on the $x$ axis, time on the $y$ axis). Your largest input should have a
runtime of *at least* an hour. The input size that gets you to an hour will
probably not be the same for the Held-Karp and Local Search implementations.

In addition to the measured runtime, plot the tour lengths obtained by both
implementations on the same input distance matrices. The length of the tour that
Held-Karp found should always be less than or equal to the tour length that
Local Search found. Why is this?

Add the code to run your experiments, graphs, and an explanation of what you did
to this markdown file.

I have been unable to complete this assignment as outlined by the given deadline. Seeing as it is marked as required to pass, I will do my best to analyze these functions without running the empirical tests and hope that this plus the completion of other coding assignments can make up for this being incomplete. HeldKarp uses dynamic programming and much more streamlined approach that guarantees finding the shortest solution to the TSP problem by recursively checking the unique paths within unique subsets of cities. Local Search uses the two opt swap algorithm to perform a local search of a randomized route. This is in essence, brute force, however my implementation utilizes a stop condition that halts the search when a certain amount of iterations go by without making any improvement to the path. Because the route is randomized with no memoization or strategy, this algorithm is not actually guaranteed to check every path before stopping, and thus not guaranteed to find the shortest path. This is why the length found by the heldkarp algorithm should always be less than our equal to the length of the path found by local search. We would expect results when graphed to show much more eratic behaviour from local search, both in it accuracy and in its runtime. If it finds a new shortest path on the last iteration before reaching the stop condition, it resets the stop condition, which could lead to extremely long runtimes in the worst cases. Heldkarp is much more methodical, and we would expect it to much more closely resemble its asymptotic runtime.
