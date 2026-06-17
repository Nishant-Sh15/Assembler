# Hack Assembler

An assembler for the Hack computer platform built as part of the **Nand2Tetris** course.

The assembler translates Hack assembly language (`.asm`) programs into Hack machine code (`.hack`) that can be executed on the Hack CPU.

## Features

* Supports all Hack A-instructions (`@value`)
* Supports all Hack C-instructions (`dest=comp;jump`)
* Handles symbolic labels `(LABEL)`
* Supports predefined symbols (`R0-R15`, `SCREEN`, `KBD`, etc.)
* Allocates memory addresses for user-defined variables
* Performs a two-pass assembly process for symbol resolution

## Project Structure

```text
assembler/
├── src/
├── test/
└── README.md
```

## Assembly Process

The assembler works in two passes:

### Pass 1

* Scans the program for label declarations.
* Builds a symbol table containing label addresses.

### Pass 2

* Translates instructions into 16-bit Hack machine code.
* Resolves labels and variables using the symbol table.

## Example

### Input (`Add.asm`)

```asm
@2
D=A
@3
D=D+A
@0
M=D
```

### Output (`Add.hack`)

```text
0000000000000010
1110110000010000
0000000000000011
1110000010010000
0000000000000000
1110001100001000
```

## Technologies Used

* Python

## About Nand2Tetris

This project was developed while working through the **Nand2Tetris** course, which guides students through building a complete computer system from basic logic gates to modern software abstractions.

## References

* Nand2Tetris Course
* The Elements of Computing Systems
