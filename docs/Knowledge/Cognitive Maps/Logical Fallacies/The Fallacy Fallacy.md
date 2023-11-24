---
title: The Fallacy Fallacy
description: logical fallacies, the fallacy fallacy
---

# [The Fallacy Fallacy](https://philarchive.org/archive/ABETFF-2)

```mermaid
graph TD
    A[Argument presented] -->|Contains a fallacy| B[Fallacious Argument]
    B --> C[Conclusion of the Argument]
    A -->|Assumed| D[Argument is Invalid]
    D --> E[Conclusion is False]
    E --> F[Fallacy Fallacy]
    style F fill:#f9d5e5
    
    subgraph Fallacy Fallacy
    D
    E
    F
    end
    
    subgraph Original Claimed Argument
    A
    B
    C
    end
    
    click F callback "Fallacy Fallacy: Assuming that because an argument contains a fallacy, the conclusion must be false."
```

- Assuming that because a claim has been poorly argued, or a fallacy has been made, that the claim itself must be wrong.
- It's possible to make a claim that is false yet argue with logical coherency for that claim, just as it's possible to make a claim that is true and justify it with other fallacies and poor arguments.

!!! Example "Fallacy Fallacy Example"
    Recognising that Chloe had committed a fallacy in arguing that we should eat healthy food because a nutritionist said it was popular, Jamie Oliver said we should therefore double cheeseburgers every day.
