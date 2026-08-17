## 2024-05-18 - [Optimizing `clock_gettime_fake`]
**Learning:** [Replacing `tick % freq` with `tick - (tick / freq) * freq` when `tick / freq` is already calculated can avoid a redundant multi-instruction math logic for 64-bit integer modulus, giving the compiler the exact opportunity to remove overhead where it might not detect identical division nodes dynamically due to side effects]
**Action:** [Always reuse quotients for matching modulo expressions using `var - quotient * divisor` to explicitly remove modulo divisions overhead in C].
