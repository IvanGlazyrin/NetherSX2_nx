
## 2024-05-18 - Binding `std::string_view` to Temporaries
**Learning:** When refactoring functions to return `std::string_view` (like `trim`), binding the view to a temporary string returned from `std::string::substr()` is illegal and causes Use-After-Free (UAF), as the temporary object is destroyed immediately. However, if the underlying string object has sufficient lifetime, `std::string_view::substr` does not allocate memory and returns a safe view into the same data.
**Action:** Always ensure `std::string_view` represents a slice of a stable buffer. When capturing parsed keys or values in data structures (like maps), perform a final conversion from `std::string_view` to `std::string` to safely duplicate the memory when needed.
