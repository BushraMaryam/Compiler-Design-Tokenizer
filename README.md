# Arithmetic Expression Tokenizer & Parser

> **A lexer and recursive descent parser built from scratch — no parsing libraries. Implements proper operator precedence (BODMAS) with descriptive error handling.**

Academic project at NED University (Compiler Design module). Demonstrates core compiler fundamentals: lexical analysis, syntax parsing, and expression evaluation — all implemented from first principles.

---

## What It Covers

This project implements the full frontend pipeline of a compiler/interpreter:

```
Input String: "3 + 5 * 2 - 8 / 4"
       │
       ▼
┌─────────────┐
│    Lexer    │  Regex-based token matching
│  (Tokenizer)│  → [INT(3), PLUS, INT(5), MUL, INT(2), MINUS, INT(8), DIV, INT(4)]
└─────────────┘
       │
       ▼
┌─────────────┐
│   Parser    │  Recursive descent with precedence rules
│             │  term() handles */ before expression() handles +-
└─────────────┘
       │
       ▼
  Result: 13   (3 + 10 - 2 = 11... correctly respects BODMAS)
```

---

## Features

- **Regex-based lexer**: Matches integers and operators (`+`, `-`, `*`, `/`)
- **Operator precedence**: `*` and `/` evaluated before `+` and `-` (BODMAS)
- **Left-to-right evaluation**: Correct associativity
- **Descriptive errors**: Clear messages for invalid tokens or syntax errors
- **No external parsing libraries**: Pure Python from scratch

---

## Repository Structure

```
compiler-design-tokenizer/
├── notebooks/
│   └── Tokenization.ipynb   # Full lexer + parser implementation
└── README.md
```

---

## Tech Stack

- **Language**: Python
- **Tools**: `re` (regex), core Python only — no parsing libraries

---

## Quick Start

```bash
git clone https://github.com/bushramaryam/compiler-design-tokenizer
```

Open `notebooks/Tokenization.ipynb` — no additional dependencies needed beyond Python standard library.

---

## Concepts Demonstrated

| Concept | Implementation |
|---------|---------------|
| Lexical Analysis | Regex tokenizer splitting input into typed tokens |
| Syntax Parsing | Recursive descent parser with grammar rules |
| Operator Precedence | `term()` for `*/`, `expression()` for `+-` |
| AST Evaluation | Direct evaluation during parse (no separate AST tree) |
| Error Handling | `SyntaxError` with positional messages |

---

## Grammar

```
expression := term (('+' | '-') term)*
term       := factor (('*' | '/') factor)*
factor     := INTEGER
INTEGER    := [0-9]+
```

---

## Author

**Bushra Maryam** — AI & Backend Engineer  
[LinkedIn](https://www.linkedin.com/in/bushra-maryam/) · [GitHub](https://github.com/BushraMaryam) · [Portfolio](https://bushramaryam.github.io)
