# Uncommon Assembly Bug: Conditional Memory Access Violation

This repository demonstrates a subtle assembly code bug that causes a memory access violation under specific conditions.  The error is conditional and might not be easily reproducible, making it an uncommon yet critical issue. The bug involves incorrect address calculation that can lead to accessing memory outside the allocated range resulting in segmentation faults.

## Bug Description
The core of the problem lies in the way memory address is computed.  A specific combination of register values (`ebx` and `ecx`) will result in an out-of-bounds memory access. The vulnerability is not apparent in routine scenarios, making it particularly difficult to detect.

## How to Reproduce
The `bug.asm` file contains the erroneous code.  To reproduce, compile and run it with different values for `ebx` and `ecx` to observe the error under specific condition. Note that this may require a specific assembler and environment, depending on the targeted architecture and operating system.

## Solution
The `bugSolution.asm` file provides a corrected version of the code.  The solution involves adding input validation and boundary checks to ensure that the calculated memory address always falls within safe limits.