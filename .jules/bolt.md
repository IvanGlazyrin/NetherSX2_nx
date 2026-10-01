## 2024-05-18 - Optimized JSON string parsing

**Learning:** Optimizing `std::string` character-by-character parsing by using `std::string::find_first_of` to locate the nearest escape or termination character avoids evaluating multiple conditionals for every standard character. When reading JSON APIs in C++, replacing manual `while`/`for` loops over characters with chunked `std::string::append` blocks dramatically speeds up parsing large string fields by performing block copies (`memcpy`) under the hood instead of repeated reallocation and char appending.
**Action:** Always prefer vectorized or SIMD-friendly lookup methods like `find_first_of` combined with `std::string::append` to skip over large runs of non-escaped characters when decoding strings.
