## 2024-05-24 - [O(N^2) String Concatenation Pattern]
**Learning:** Found instances of Schlemiel the Painter algorithm (using `strncat` inside loops with `strlen`) which causes O(N^2) performance when building large strings in C.
**Action:** Always replace `strncat`/`strcat` in loops with `memcpy`/direct assignment tracking the current length (`out_len`), reducing time complexity to O(N).
