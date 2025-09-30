# Compilers Introduction

### Compilers vs Interpreters

Answered Exercises

1. **What is the difference between compiler and an interpreter?**
    - Simply stated, a compiler is a program that can read a program in onelanguage — the source language — and translate it into an equivalent program in another language — the target language. An important role of the compiler is to report any errors in the source program that it detects during translation.
    - An interpreter is another common kind of language processor. Instead of producing a target program as a translation, an interpreter appears to directly execute the operations specified in the source program on inputs supplied by the user.
2. **What are the advantages of (a) a compiler over an interpreter (b) an interpreter over a compiler?**
    - The machine-language target program produced by a compiler is usually much faster than an interpreter at mapping inputs to outputs.
    - An interpreter, however, can usually give better error diagnostics than a compiler, because it executes the source program statement by statement.

Unanswered Exercises

4. **What advantages are there to a language-processing system in which the compiler produces assembly language rather than machine language?**
    - Because assembly is easier to produce as output and is easier to debug. The assembly.
5. **A compiler that translates a high-level language into another high-level language is called a source-to-source translator. What advantages are there to using C as a target language for a compiler**
6. **Describe some of the tasks that an assembler needs to perform.**


### The structure of a Compiler
Compiler has two parts
- **Analysis** (frontend)
    - detects syntax or sematic errors.
    - genrates symbol table + code's intermediate representation
- **Synthesis** (backend)
    - generates program based analysis output.

They may be divided into 6 or 7 parts
- **Lexical Analyzer** (Characters ➝ Tokens)
    - A token may be tuple of (tokenName , attributeValue) (like: (id,0) for an identifier , (=,null) for assignment operator)
- **Syntax Analyzer** (Tokens ➝ Syntax Tree)
- **Semantic Analyzer** (Syntax Tree ➝ Syntax Tree)
    - checks the source program for semantic consistency with the language definition.
    - gathers type information and saves it in either the syntax tree or the symbol table
- **Intermediate Code Generator** (Syntax Tree ➝ Intermediate Code (eg. ***three address*** code) )
    - easy to produce
    - easy to transalte to target machine
- **Intermediate Code Optimizer** (Code ➝ Code)
    - produces better code (faster or smaller or whatever is the objective)
- **Code Generator** (Intermediate Code ➝ Target Machine Code)

**Note:** Code optimizer may exist for target machine code or intermediate code or both.

**Symbol Table** is a structure containing all defined variabls/functions and their information.

Multiple compiler phases may be grouped into **passes**. A **pass** is a component whose input & output are files.
For example we may group phases from lexical analyzer to intermediate code generator in one pass, code optimizer in a second optional pass and target machine code generator a final pass.

**Up Next:** 1.2.9 Compiler-Construction Tools