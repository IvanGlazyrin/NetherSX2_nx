## 2024-05-24 - [O(N^2) String Concatenation Bottleneck]
**Learning:** Calling `strncat` sequentially with `strlen(out)` inside a loop causes O(N^2) time complexity (Shlemiel the Painter's algorithm), particularly in `jni_fake.c` string list aggregations.
**Action:** When appending strings in a loop, track the length locally and use `memcpy` or direct pointer assignment instead of `strncat` and `strlen` combinations.
