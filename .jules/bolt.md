
## 2024-05-24 - Avoiding unnecessary `substr` allocations
**Learning:** Passing `string.substr(offset)` into string processing functions triggers memory allocations for temporary `std::string` objects.
**Action:** Instead, modify the receiving functions to take an optional `offset` parameter and operate directly on the original string's view. This is especially true for helper functions like `trim_copy` which use finding mechanisms that can accept an offset. Also include a fast-path return (`if (first == 0 && last == value.size()) return value;`) to avoid `.substr()` overhead when the string requires no changes.
