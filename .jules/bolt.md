## 2024-05-17 - [Optimizing Hot Path Loops on Idle State]
**Learning:** Checking for state changes before processing expensive loops inside input handlers avoids unnecessary processing on idle loops. The `update_gamepads` method runs constantly in the main loop every frame, but button presses and stick movements occur significantly less often, so bypassing the inner loops can drastically reduce idle load.
**Action:** Always check if states changed in the current frame and exit early in update-loops before evaluating complex bindings and looping through configurations.
