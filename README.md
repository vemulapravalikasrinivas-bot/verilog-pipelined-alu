# verilog-pipelined-alu
A pipelined ALU design in Verilog supporting arithmetic and logical operations with signed operands and overflow detection.

# Pipelined ALU in Verilog

This project implements a pipelined Arithmetic Logic Unit (ALU) using Verilog HDL.  
The design supports signed arithmetic operations and logical operations with overflow detection.

## Features
- Parameterized bit-width (N-bit)
- Signed arithmetic support
- Pipelined architecture
- Operations:
  - Addition
  - Subtraction
  - Bitwise AND
  - Bitwise OR
  - XOR
  - NOT
  - Arithmetic shift left
  - Arithmetic shift right
- Overflow detection for arithmetic operations

## Inputs
- `a`, `b`: Signed operands
- `sel`: Operation select
- `clk`: Clock signal
- `reset`: Reset signal

## Outputs
- `out`: Result (N-bit signed)
- `overflow`: Overflow flag

## Operation Table

| sel | Operation |
|-----|----------|
| 000 | Addition |
| 001 | Subtraction |
| 010 | NOT |
| 011 | OR |
| 100 | AND |
| 101 | XOR |
| 110 | Arithmetic Right Shift |
| 111 | Arithmetic Left Shift |

## Design Architecture
The design consists of:
1. Input register stage
2. Combinational ALU logic
3. Output register stage

This creates a pipelined structure that improves timing performance by breaking the combinational path into stages.

## Notes
- Overflow is only meaningful for addition and subtraction.
- Shift operations use a fixed shift amount of 2 bits.
