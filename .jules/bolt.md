## 2024-05-24 - Avoid O(N^2) string concatenation in loops
**Learning:** Repeatedly calling `strncat` and `strlen` to append chunks to a buffer inside a loop results in Shlemiel the Painter's algorithm (O(N^2) complexity), as `strncat` must scan the string to find the null terminator each time.
**Action:** When concatenating strings in a loop, always track the current length (or pointer to the end) and use `memcpy` instead of `strncat` or repeated `strlen` calls.
