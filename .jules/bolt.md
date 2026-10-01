## 2024-05-18 - C String Concatenation O(N^2)
**Learning:** Found typical Shlemiel the painter's algorithm in `jni_fake.c` where `strncat` and `strlen` was used repeatedly inside a loop.
**Action:** Always refactor loop concatenations to use explicit length trackers and `memcpy` to keep the time complexity to O(N).
