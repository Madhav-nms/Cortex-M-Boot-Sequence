# Cortex-M-Boot-Sequence
This repo demonstrates how a Cortex M CPU boots after reset and begins instructions.

Using a minimal ARM assembly program and GDB, it shows: 
- how the initial stack pointer (SP/R13) is loaded from address 0x00000000
- how the program counter (PC/R15) is loaded from address 0x00000004
- how execution begins at the reset handler

## Aim 
1. Loads SP (R13) from 0x00000000
2. Loads PC (R15) from 0x00000004
3. Starts executing instructions in the reset handler
This behavior is verified step by step using QEMU and GDB.

## File Overview 

| File | Purpose |
|------|---------|
| `asm.s` | Defines the vector table and the reset handler |
| `map.ld` | Linker script that places the vector table at address `0x00000000` |
| `Makefile` | Builds the .elf and launches QEMU with GDB support |
| `asm.elf` | Final linked executable used by QEMU |
| `asm.elf.lst` | Disassembly listing of the ELF |
| `asm.elf.debug` | ELF debug and symbol information |
| `images/` | GDB screenshots showing reset state and instruction execution |
