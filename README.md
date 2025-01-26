# Uncommon VHDL Counter Overflow Bug
This repository demonstrates a subtle bug in a VHDL counter implementation. The counter works as expected in most basic scenarios but might show unexpected behaviour in more complex systems.

## Bug Description
The `buggy_counter.vhd` file contains a VHDL counter that counts from 0 to 15. When the counter reaches 15, it resets to 0. While this seems correct at first glance, it might lead to unexpected behavior in scenarios where the counter's overflow is not handled properly in the surrounding system. The subtle issue may be difficult to detect in simulations if the rest of the system doesn't depend on specific counter overflow behavior. 

## Solution
The `fixed_counter.vhd` file provides a corrected version of the counter.  The solution addresses the potential issue by explicitly signaling an overflow condition. This allows the surrounding system to react appropriately to the counter reaching its maximum value.

## How to reproduce
1.  Simulate `buggy_counter.vhd` in your preferred VHDL simulator.
2.  Integrate `buggy_counter.vhd` into a larger system where an overflow condition has consequences. Observe the behavior.
3.  Repeat steps 1 and 2 with `fixed_counter.vhd` to see the difference.
