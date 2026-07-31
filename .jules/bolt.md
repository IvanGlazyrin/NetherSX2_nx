## 2024-05-19 - Unconditional event polling overhead
**Learning:** Polling controllers and touches unconditionally in an event-driven emulation core generates extreme redundant JNI API overhead when inputs are idle.
**Action:** Always verify if continuous state updates are identical to previous values. Cache inputs and use early returns to filter duplicate events before crossing API boundaries.
