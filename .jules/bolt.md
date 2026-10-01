## 2024-05-24 - Schlemiel the Painter in C string parsing
**Learning:** Found O(N^2) complexity in `strncat`/`strlen` loops in string building functions inside `jni_fake.c`. Repeated `strlen(out)` calls were made inside loops to find bounds to append new string parts.
**Action:** Replaced with a length tracker `out_len` and used `memcpy`, changing the loop string concatenation complexity from O(N^2) to O(N).
