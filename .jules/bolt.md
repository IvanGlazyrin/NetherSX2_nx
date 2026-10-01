## 2024-05-18 - String Concatenation Inefficiency in jni_fake.c
**Learning:** Found O(N^2) string concatenations using `strncat(..., cap - strlen(out) - 1)` in `jni_fake.c`. Specifically in `stringlist_add` and `setStringList` (in `CallVoidMethodV`). Since `strlen(out)` is re-evaluated each time, traversing the growing string on every append makes it O(N^2), which is especially bad if these lists get large.
**Action:** Replace `strncat` with explicit length tracking and `memcpy` (or pointer manipulation) to make concatenation O(N).
