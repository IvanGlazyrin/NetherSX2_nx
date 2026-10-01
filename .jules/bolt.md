## 2024-06-25 - Shlemiel the Painter's String Concatenation
**Learning:** Found classic O(N^2) string concatenation using `strncat` combined with `strlen` within loops parsing preferences (`stringlist_add` and `setStringList` in `jni_fake.c`).
**Action:** Always replace chained `strncat`/`strlen` loops with manual length tracking (`out_len`) and `memcpy` to ensure O(N) performance for string building.
