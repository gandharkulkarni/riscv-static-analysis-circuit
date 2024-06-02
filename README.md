# RISC-V Static Analysis Circuit

## Introduction
This repository contains the digital circuit design files for a static analysis tool that processes machine code instructions for RISC-V programs. The circuit reads instructions from a ROM component and provides counts for the total number of instructions and various instruction types.

Use the Digital application to build and simulate digital circuits: https://github.com/hneemann/Digital

## Project Structure
- `project04.dig`: The main digital circuit file.
- `.hex` files: Hexadecimal representations of machine code for analysis.

## Features
- **Instruction Counting**: Tallies the total number of instructions within a RISC-V program.
- **Type Analysis**: Categorizes and counts instruction types including ITYPE, RTYPE, LOAD, STYPE, BTYPE, JAL, J, and JALR.
- **Program Selection**: A 2-bit input `PROG` allows selection among multiple programs for analysis.
- **End-of-Program Marker**: Utilizes `unimp (0xC0001073)` as a marker to signify the end of a program.

## Requirements
- The circuit must be named `project04.dig`.
- Outputs must be named as TOTAL, ITYPE, RTYPE, LOAD, STYPE, BTYPE, JAL, J, and JALR.
- Inputs include PROG, CLK, and CLR.
- Supports up to 256 instructions per program, including the end marker.

## Usage
To analyze a program, load the corresponding `.hex` file into the ROM component of the circuit and observe the output counts for each instruction type.

## Building the Circuit
The circuit utilizes Digital components such as multiplexors, encoders, decoders, gates, splitters, and wires. Custom components like adders, registers, counters, comparators, instruction storage, and analyzers are also included.

## Testing
Test the circuit with provided machine code for `fib_rec_s`, `is_pal_rec_s`, `getbit_seq_s`, and `quadratic_s`. Generate the `.hex` files using the following command:

```bash
objdump -d file.o | python3 makerom3.py > file_rom.hex
```

## Acknowledgments
Gratitude is extended to Professor Greg Benson for offering insights and suggestions to refine this circuit.