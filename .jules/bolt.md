## 2024-05-14 - [String Optimization Fast-Path]
**Learning:** Returning a by-value std::string parameter early instead of unconditionally calling .substr() allows C++11 (and later) to implicitly move the parameter into the return value. This avoids unnecessary heap allocations for strings that are already trimmed.
**Action:** Always consider fast-path early returns in string manipulation functions that accept by-value arguments.
