
## 2024-05-18 - [Fast Path Returns for SSO Overheads]
**Learning:** Returning early from string manipulation routines (like trim) if no changes are required avoids allocating new `std::string` copies or heap buffers via `.substr()`. Furthermore, taking arguments by value and passing them out exploits C++11 move semantics effectively.
**Action:** When working on string operations like `trim`, `replace`, or formatting, check for "no-op" early returns before invoking allocation-heavy methods.
