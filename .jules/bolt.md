## 2026-08-03 - [Transparent Map Hashing for C++20]
**Learning:** `std::unordered_map` text caching lookups originally re-allocated standard strings on each frame draw to hit the cache, causing heavy contention. Heterogeneous mapping (`is_transparent = void`) with `std::string_view` cleanly avoids this natively in C++20.
**Action:** When inspecting hot loops or caches in C++20 contexts, use `std::string_view` and ensure maps use transparent hashing to drastically limit allocations.
