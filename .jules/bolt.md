## 2024-05-24 - String Optimization using std::string_view
**Learning:** In C++ codebases, especially when processing string configuration lines (like cheat files or ini files), excessive copying with `std::string` during string splitting and trimming can be a measurable overhead. `std::string_view` allows string inspection and substring slicing without memory allocations.
**Action:** When finding loops or processing logic that takes `const std::string&` and makes multiple `.substr()` calls to generate temporary tokens, refactor the parameters and variables to `std::string_view`.
