## 2024-07-27 - Early string filtering vs filesystem stat()
**Learning:** In C++ code iterating through a directory (like `scanGames`), calling `stat()` and constructing full path strings via `join()` for every file is very slow.
**Action:** When filtering directory contents, always perform string matching (like checking file extensions) first to short-circuit the loop and avoid expensive I/O operations and string allocations for non-matching files.
