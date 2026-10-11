## 2024-05-23 - Avoid std::string copies in parsing loops using std::string_view
**Learning:** Using std::string passed by value or returned by value in tight string parsing loops (like `trim_copy`, `skip_space`) causes massive allocation overhead. Using `std::string_view` for parsing read-only strings avoids heap allocations, improving parsing throughput significantly.
**Action:** When parsing text blocks, use `std::string_view` for helper functions (`skip_space`, `trim_view`, `starts_with_ci`) rather than `std::string`, avoiding intermediate temporaries.
