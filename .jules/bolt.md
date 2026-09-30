## 2024-05-18 - String Parsing Optimization in C++
**Learning:** Using `std::string_view` for read-only string operations and parsing significantly reduces heap allocations compared to `const std::string&` and `.substr()` returning new strings.
**Action:** When refactoring C++ string parsing loops, prefer `std::string_view` arguments and return types. Ensure full `std::string` objects are only constructed when ownership or lifetime extension is strictly required.
