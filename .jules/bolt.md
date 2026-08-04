## 2024-08-04 - IO Operation Reordering
**Learning:** Checking memory/string properties (like file extension) should always happen before dispatching expensive system calls like `stat()`, especially in systems where the storage abstraction (like SMB or Switch libnx SD) might have large latencies per file query.
**Action:** Order conditionals by cost, placing CPU/memory-bound short-circuit evaluations before IO/syscalls.
