## 2024-05-24 - [Avoid Incomplete Types in Mock Static Checks]
**Learning:** When using `g++ -fsyntax-only` with isolated dummy headers on C++ source files, passing POSIX macro definitions like `-D_POSIX_C_SOURCE=200809L` may be necessary to unlock structs (e.g., `stat`) defined inside standard headers like `<sys/stat.h>`, preventing false-positive incomplete type errors.
**Action:** Use `-D_POSIX_C_SOURCE=200809L` during syntax checks if standard POSIX types throw errors despite standard library inclusion.
