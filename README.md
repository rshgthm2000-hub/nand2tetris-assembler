# Nand2Tetris Assembler (C++)

A **Hack Assembler** implementation for the **Nand2Tetris** course, written in **C/C++**.
This project translates Hack assembly language (`.asm`) into Hack machine code (`.hack`) as specified in **Project 6** of the Nand2Tetris curriculum.

---

## 📌 Project Overview

The assembler performs a **two-pass translation**:

1. **First Pass** – Builds the symbol table by handling labels.
2. **Second Pass** – Translates A-instructions and C-instructions into binary machine code.

It supports:

* A-instructions (`@value`, `@symbol`)
* C-instructions (`dest=comp;jump`)
* Labels (`(LABEL)`)
* Predefined symbols (e.g., `SP`, `LCL`, `ARG`, `THIS`, `THAT`, `R0–R15`, `SCREEN`, `KBD`)

---

## 📂 File Structure

```
├── assembler.c     // Main assembler logic and control flow
├── assembler.h     // Assembler declarations
├── parser.c        // Parses Hack assembly instructions
├── parser.h        // Parser interface and enums
├── writer.c        // Converts parsed instructions to binary
├── writer.h        // Binary code writer interface
├── README.md       // Project documentation
```

---

## ⚙️ How It Works

### Parser

* Removes whitespace and comments
* Identifies instruction types:

  * A-instruction
  * C-instruction
  * Label

### Symbol Table

* Stores predefined symbols
* Adds labels during the first pass
* Allocates memory for variables starting at address 16

### Code Writer

* Converts `dest`, `comp`, and `jump` mnemonics into binary
* Outputs 16-bit Hack machine instructions

---

## 🚀 Build & Run

### Compile

```bash
gcc assembler.c parser.c writer.c -o assembler
```

### Run

```bash
./assembler input.asm
```

### Output

* Generates `input.hack` in the same directory

---

## 🧪 Example

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

---

## 📚 Nand2Tetris Reference

* Course: *From Nand to Tetris – Building a Modern Computer from First Principles*
* Project: **Assembler (Project 6)**

---

## 🛠️ Technologies Used

* **C / C++**
* Standard C libraries
* GCC compiler

---

## ✨ Features

* Clean modular design (Parser, Assembler, Writer)
* Follows official Hack specification
* Efficient symbol handling

---

## 📄 License

This project is for **educational purposes** as part of the Nand2Tetris course.

---

## 🙋‍♀️ Author

**Garima Badugu**
CS Student | Systems & Low-level Programming Enthusiast

---

⭐ If you find this project helpful, consider giving it a star!
