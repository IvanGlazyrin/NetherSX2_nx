## 2024-06-19 - Temporary files in PRs
**Learning:** Leftover scratchpad files and mock header files created to bypass static analysis dependency issues will be rejected during code review as they pollute the codebase and break the build system.
**Action:** Always ensure all dummy files, scratchpads, and temporary include directories are explicitly deleted via `rm -rf` before calling `request_code_review` or `submit`.
