## 2024-08-01 - O(n^2) String Construction via strncat
**Learning:** Using `strncat` in a loop repeatedly scans the destination string to find the null terminator, leading to Shlemiel the Painter's algorithm with O(N^2) complexity. This is common when joining delimited string arrays in C without tracking the offset.
**Action:** Always maintain an explicit `out_len` tracking variable and use `memcpy` to write directly to the correct offset, achieving O(N) linear time complexity for string building.
