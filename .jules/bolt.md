## 2024-05-18 - Optimize fix_path early exit
**Learning:** The emulator frequently intercepts file system operations using `fix_path` in `libc_shim.c` to translate Android app paths into paths inside the Nintendo Switch data folder. This happens for every `open`, `mkdir`, `stat`, and `remove`.
**Action:** When working on shims or interceptors for file paths, always include an early exit fast-path that quickly bails out of any processing for the majority of non-matching standard cases to avoid repeated loops and `strlen()` / `strncmp()` calls.
