## 2024-06-12 - Prevent O(N^2) complexity in C string concatenation loops
**Learning:** Using `strncat(out, str, cap - strlen(out) - 1)` inside loops introduces an O(N^2) complexity ("Shlemiel the Painter's algorithm") because both `strlen` and `strncat` rescan the output buffer from the start on every iteration.
**Action:** When building strings in C loops, maintain an explicit `out_len` tracker and copy substrings directly to the tail using `memcpy(out + out_len, str, len)` to ensure O(N) performance.
