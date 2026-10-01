## 2024-05-24 - Shlemiel the Painter in C String Concatenation
**Learning:** Found O(N^2) complexity string concatenation patterns using repeated `strncat` and `strlen` in `source/jni_fake.c`. When concatenating inside a loop, `strncat` repeatedly calculates the length of the destination string, causing performance degradation as the string grows.
**Action:** Always maintain an explicit length tracker (`out_len`) and use `memcpy` for successive string appends inside loops in C/C++ to guarantee O(N) complexity.
