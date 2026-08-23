
## 2024-05-24 - [Avoid temporary objects and unneeded dynamic allocations in string trimming]
**Learning:** `std::string::find_first_not_of` and `find_last_not_of` incur overhead inside tight loops because of their inner table/lookup operations. Moreover, creating substrings via `s.substr()` when the string is already trimmed performs redundant heap allocations.
**Action:** When working in performance-critical paths (e.g., config parsing files), prefer manual loops with direct index/pointer evaluation for small sets of characters. When the string remains unmodified, bypass `.substr()` to trigger NRVO (Named Return Value Optimization) / copy elision and avoid redundant memory allocations.
