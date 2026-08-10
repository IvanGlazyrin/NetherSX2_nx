## 2024-08-10 - String view for configuration parsing
**Learning:** Found an opportunity to replace std::string by-value returns and arguments with std::string_view for INI file parsing, drastically reducing string allocations. When replacing std::string with std::string_view, we must manually instantiate std::string again when storing into maps since the buffer is temporary.
**Action:** Always look for std::string passed by value or returned from small parser functions (like trim) where a string_view can eliminate heap allocations.
