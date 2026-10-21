## $(date +%Y-%m-%d) - Optimize O(N^2) string concatenations
**Learning:** In C/C++, repeatedly using `strncat` or calling `strlen` on an accumulating buffer in a loop causes Schlemiel the Painter's algorithm, resulting in O(N^2) complexity because it must re-scan the entire string length on every iteration.
**Action:** When building strings in a loop, maintain a local length tracker (e.g., `size_t out_len`) and use `memcpy` to append directly at the end of the buffer, which reduces the time complexity to O(N).
