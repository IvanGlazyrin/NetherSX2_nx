
## 2024-05-24 - Rejecting `return s` in `std::string` returning functions
**Learning:** Adding a fast path like `if (trimmed) return s;` to a function taking `const std::string&` and returning `std::string` by value is a failed optimization. It invokes the copy constructor, which still causes allocation and memcopy if the string exceeds SSO capacity.
**Action:** Do not attempt fast-path `std::string` returns unless the return type is changed to `std::string_view` (which breaks ABI/API) or the caller passes an out parameter.
