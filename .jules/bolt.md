
## 2024-05-30 - Optimize string parsing logic using std::string_view
**Learning:** In string parsing functions in C++, passing parameters by `const std::string&` and using `trim_copy` implementations returning new `std::string` instances by value involves redundant and unnecessary memory allocations.
**Action:** Instead of `std::string`, use `std::string_view` for string parsing arguments where they do not need modification, and implement helpers like `trim_view(std::string_view)` to replace allocations with safe substring references.

## 2024-05-30 - Optimize file path concatenation
**Learning:** `snprintf` format parsing in C is often a noticeable overhead during performance-sensitive tasks like directory iteration, especially when concatenating strings where exact lengths are easily verifiable.
**Action:** Use `strlen` and `memcpy` for fast string assembly when paths are known to fit in the buffer, and rely on `snprintf` strictly as a fallback.
