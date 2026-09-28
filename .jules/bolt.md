## 2024-05-24 - Optimizing String Parsing
**Learning:** In C++ codebases, functions processing string subsets (like `Trim` or tokenizers) often inadvertently trigger memory allocations when using `std::string` return types and `substr`.
**Action:** Replace `std::string` parameters and return types with `std::string_view` for read-only string manipulation, such as in configuration parsing loops, to completely avoid intermediate heap allocations.
