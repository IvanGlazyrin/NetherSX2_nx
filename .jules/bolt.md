## 2024-05-24 - O(N^2) String Join Optimization
**Learning:** Found classic Schlemiel the Painter's algorithm (O(N^2) complexity) during string concatenations when looping in `jni_fake.c` via repeated `strncat(..., strlen(...))` calls.
**Action:** Used length tracking `out_len` and `memcpy` instead to perform string combinations in a single pass O(N), replacing `strncat`. Carefully ensured loop logic handles trailing or leading newlines accurately without changing string splitting behaviour.
