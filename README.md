# VHDL Counter with Race Condition and Potential Overflow

This repository demonstrates a common VHDL coding error leading to a race condition and potential integer overflow in a simple counter.

## The Bug

The `buggy_counter.vhdl` file contains a counter that increments on each rising clock edge, resetting to 0 when it reaches 15.  However, it has a potential race condition in the `if rst = '1'` section, and lacks a robust reset handling mechanism. Depending on how the simulator handles the simultaneous events of the clock edge and reset, it might lead to unpredictable behavior.

## The Solution

The `fixed_counter.vhdl` shows a corrected implementation that addresses both the race condition by using a separate process for reset, and initializes the internal count explicitly before the counter starts to function, preventing undefined behavior or potential overflow errors.