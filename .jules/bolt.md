## 2024-06-25 - Shlemiel the Painter in C stringlist functions
**Learning:** Found O(N^2) string concatenation using `strncat` and `strlen` repeatedly inside loops in JNI fake implementation (`stringlist_add` and `setStringList`). This anti-pattern becomes a severe bottleneck as the list of items grows.
**Action:** Replaced with `memcpy` and a length tracker (`out_len`), optimizing the complexity to O(N) by manually maintaining the buffer index.
