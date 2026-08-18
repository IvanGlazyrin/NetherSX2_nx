
## 2024-05-18 - [Optimize scanGames I/O overhead and ellipsizedText string allocations]
**Learning:** [Reordering boolean conditions to evaluate a fast string-based check before a slow filesystem stat call takes advantage of short-circuit evaluation without altering logical outcome, drastically reducing filesystem overhead during directory scans. Adding an early-return fast-path for text that already fits avoids expensive boundary scan and dynamic string allocations.]
**Action:** [Look for slow system calls combined with fast predicate checks, and make sure the fast predicate check is evaluated first to take advantage of short-circuit evaluation. Similarly, check for boundary conditions early on to avoid deep processing where it's not needed.]
