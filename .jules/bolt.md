## 2023-10-27 - O(N^2) String Concatenation Pattern
**Learning:** Found O(N^2) string concatenation patterns in `jni_fake.c` and `main.c` where `strncat` or `strlen` are repeatedly called in loops or vararg appends. This triggers Shlemiel the Painter's algorithm since the string length must be scanned from the start on every iteration.
**Action:** Replace `strncat` in loops with direct length tracking and memory copies, and update `text_append` to maintain length or use returned length from `snprintf` when appending strings.
