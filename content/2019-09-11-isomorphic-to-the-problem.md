+++
title = "Isomorphic to the Problem"
date = "2019-09-11"
[taxonomies]
tags = ["complexity", "Joe Armstrong"]
+++

> The structure of the program should exactly follow the structure of the problem. Each real world concurrent activity should be mapped onto exactly one concurrent process in our programming language. If there is a 1:1 mapping of the problem onto the program we say that the program is isomorphic to the problem.
>
> It is extremely important that the mapping is exactly 1:1. The reason for this is that it minimizes the conceptual gap between the problem and the solution. If this mapping is not 1:1 the program will quickly degenerate, and become difficult to understand. This degeneration is often observed when non-CO [concurrency-oriented] languages are used to solve concurrent problems. Often the only way to get the program to work is to force several independent activities to be controlled by the same language thread or process. This leads to an inevitable loss of clarity, and makes the programs subject to complex and irreproducible interference errors.

— Joe Armstrong, [_Making reliable distributed systems in the presence of software errors_][1]&nbsp;(2003)

[1]: https://erlang.org/download/armstrong_thesis_2003.pdf
