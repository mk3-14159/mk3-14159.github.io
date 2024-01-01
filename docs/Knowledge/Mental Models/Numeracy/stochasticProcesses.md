---
title: Stochastic Processes
description: Numeracy, Stochastic Processes
---

# [Stochastic Processes](https://en.wikipedia.org/wiki/Stochastic_process)

```mermaid
graph TD;
    A[Start] -->|Initial State| B(Random Event 1)
    B -->|Outcome 1| C[State 2]
    B -->|Outcome 2| D[State 3]
    C -->|Next Random Event| E[State 4]
    D -->|Next Random Event| F[State 5]
    E --> G[...]
    F --> H[...]

style A fill:#f9f,stroke:#333,stroke-width:2px
style B fill:#fc0,stroke:#333,stroke-width:2px
style C fill:#0f0,stroke:#333,stroke-width:2px
style D fill:#0ff,stroke:#333,stroke-width:2px
style E fill:#f99,stroke:#333,stroke-width:2px
style F fill:#99f,stroke:#333,stroke-width:2px
style G fill:#fff,stroke:#333,stroke-width:2px
style H fill:#fff,stroke:#333,stroke-width:2px
```

- A stochastic process is a random statistical process and encompasses a wide variety of processes in which the movement of an individual variable can be impossible to predict but can be thought through probabilistically. 

- The wide variety of stochastic methods helps us describe systems of variables through probabilities without necessarily being able to determine the position of any individual variable over time. 

!!! example "Example of Stochastic Processes"
    It’s not possible to predict stock prices on a day-to-day basis, but we can describe the probability of various distributions of their movements over time. Obviously, it is much more likely that the stock market (a stochastic process) will be up or down 1% in a day than up or down 10%, even though we can’t predict what tomorrow will bring.
