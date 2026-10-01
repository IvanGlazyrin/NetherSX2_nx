## 2024-05-08 - O(n^2) String Concatenation Pattern
**Learning:** Found a specific anti-pattern in `source/jni_fake.c` where `strncat(out, ..., cap - strlen(out) - 1)` was used inside loops for string arrays and token parsing. This causes an O(N^2) "Shlemiel the Painter" algorithm because it recalculates `strlen` and traverses the entire string from the beginning on every loop iteration.
**Action:** When performing multiple string concatenations or building strings in a loop, maintain a manual `out_len` counter and use `memcpy(out + out_len, ...)` to achieve O(N) linear time performance.
