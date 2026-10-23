
## 2024-05-18 - CheatManager String View Optimization
**Learning:** In code dealing with numerous small parsing operations (like `.pnach` files), passing `std::string` by value or `const std::string&` while constructing substrings can result in thousands of temporary heap allocations per parsing run.
**Action:** Always prefer `std::string_view` for read-only string manipulation, trimming, and prefix checking. It eliminates heap allocations for substrings by passing lightweight fat-pointers. Note: ensure views are not accidentally bound to `std::string` temporaries, and construct real `std::string` only at the final point of assignment.
