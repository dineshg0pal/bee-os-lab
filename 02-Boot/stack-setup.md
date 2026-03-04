🪵 Stack Setup
What is a Stack?

The stack is a memory area where the CPU stores temporary data like function calls, local variables, and return addresses.
Think of it as a “to-do stack”: last thing added is the first thing used (LIFO).

Why Bee Kernel Needs It

Keeps track of function calls

Stores CPU state during interrupts

Provides safe space for kernel & user code

Kernel Stack
uint8_t kernel_stack[4096];
uint32_t kernel_stack_top = (uint32_t)&kernel_stack[4096];

Ring 0 stack for kernel operations

Used when switching to kernel mode or handling interrupts

User Stack

Separate stack for user programs

Ensures kernel and user don’t overwrite each other

Usually placed in higher memory like 0x00800000

Quick Notes

Always initialize before enabling interrupts

Stack top points to the highest memory address of the stack

Protects kernel integrity
