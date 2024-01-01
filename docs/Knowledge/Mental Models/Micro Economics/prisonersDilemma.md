---
title: Prisoner's Dilemma
description: Micro Economics, Prisoner's Dilemma
---

# [Prisoner's Dilemma](https://en.wikipedia.org/wiki/Prisoner%27s_dilemma) 

```mermaid
graph TD
    A[Prisoner A] -->|Testifies| B((Betrays))
    A -->|Remains Silent| C((Silent))
    D[Prisoner B] -->|Testifies| E((Betrays))
    D -->|Remains Silent| F((Silent))
    B -->|A: 3 years, B: 0 years| G[Outcome 1]
    C -->|A: 0 years, B: 3 years| H[Outcome 2]
    E -->|A: 3 years, B: 0 years| I[Outcome 3]
    F -->|A: 0 years, B: 3 years| J[Outcome 4]
    B -->|Both: 2 years| K[Outcome 5]
    E -->|Both: 2 years| K

style A fill:#f9d5e5, stroke:#333
style D fill:#f9d5e5, stroke:#333
style B fill:#84b6f4, stroke:#333
style C fill:#84b6f4, stroke:#333
style E fill:#84b6f4, stroke:#333
style F fill:#84b6f4, stroke:#333
style G fill:#f6ab6c, stroke:#333
style H fill:#f6ab6c, stroke:#333
style I fill:#f6ab6c, stroke:#333
style J fill:#f6ab6c, stroke:#333
style K fill:#f6ab6c, stroke:#333
```

- The Prisoner’s Dilemma is a famous application of [game theory](https://en.wikipedia.org/wiki/Game_theory) in which two prisoners are both better off cooperating with each other, but if one of them cheats, the other is better off cheating. Thus the dilemma. 

- This model shows up in economic life, in war, and in many other areas of practical human life. Though the prisoner’s dilemma theoretically leads to a poor result, in the real world, cooperation is nearly always possible and must be explored.

!!! example "Example of Prisoner's Dilemma"
    Two criminals are arrested, but the police lack sufficient evidence for a conviction; the police separate the prisoners and offer each the same deal: if one testifies against the other and the other remains silent, the betrayer goes free while the silent accomplice receives the full sentence.