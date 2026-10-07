## 2023-10-27 - [Avoid std::string allocations in Trim functions]
**Learning:** Passing std::string by value and returning string from .substr() in text parsing routines (like Trim/ReadIni) causes O(N) redundant allocations per line.
**Action:** Prefer using std::string_view as function arguments and return types for text scanning functions, and only explicitly instantiate std::string when storing the result.
