## 2024-05-14 - String View Parsing Optimization
**Learning:** Using `const std::string&` in utility string parsing methods (like `skip_space` or `trim_copy`) forces the creation of intermediate `std::string` copies whenever `std::string::substr()` is passed into the functions, increasing memory allocations.
**Action:** Always prefer `std::string_view` over `std::string` as parameters and return types for pure, non-mutating parsing functions to prevent temporary heap allocations.
