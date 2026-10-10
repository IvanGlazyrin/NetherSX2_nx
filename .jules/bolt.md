
## 2024-05-18 - Replacing `std::string` allocations with `std::string_view` in Cheat Parsing
**Learning:** In tight loops parsing text files (like cheat files), passing `std::string` by value or returning `std::string` copies (e.g., in a `trim_copy` function) causes extensive dynamic memory allocation overhead. Replacing these with `std::string_view` significantly accelerates parsing by avoiding heap allocations during substr and trimming operations.
**Action:** When implementing read-only string manipulation utilities in C++17/20 (like parsers, trimmers, or tokenizers), prefer passing and returning `std::string_view` over `const std::string&` to eliminate unnecessary copy allocations and drastically improve processing speed.
