
## 2024-05-18 - Replacing string by value with string_view in parsing logic
**Learning:** Utilizing `std::string_view` for parsing cheat files eliminates dynamic allocations caused by copying sub-strings when using `std::string::substr` and passing string by value. However, one must remember that explicit conversion via `std::string(string_view_obj)` is required if assigning back to a `std::string`.
**Action:** Always favor `std::string_view` in read-only parsing functions in C++17+ codebases to avoid heap allocations. Ensure explicit conversions are applied where an owning `std::string` is strictly required.
