## 2023-10-24 - JSON parsing vector placement
**Learning:** In C++ string manipulation, using `std::string::substr()` directly inside an `emplace_back` call forces a temporary string object to be allocated and then immediately moved/copied into the vector.
**Action:** Use the placement constructor `emplace_back(str, pos, count)` to construct the string directly into the vector element's memory in-place, eliminating the intermediate allocation.

## 2023-10-24 - Bulk appending vs char-by-char reading
**Learning:** Iterating byte-by-byte and using `operator+=` for strings with complex inner state conditionals (like JSON escaping) forces the CPU branch predictor to work hard and incurs frequent memory relocation checks.
**Action:** Use `find_first_of` to leap across unescaped segments and `append()` to bulk-copy valid chunks, falling back to special handling only when an escape character is explicitly encountered. This dramatically reduces inner-loop operations on the fast path.
