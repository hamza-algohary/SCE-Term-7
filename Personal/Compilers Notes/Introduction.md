# Compilers Introduction

### Compilers vs Interpreters
[Exercise](exercises/1.1.md)

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

### Some Compiler Construction Tools
1. **Parser Generator** produces a syntax analyzer from language description
2. **Scanner Generator** produces a lexer from regular expressions
3. **Syntax Directed Translation Engine** produces a converter of syntax trees to intermediate code
4. **Code Generator Generator** produces a code generator from translation rules from intermedia-code to target machnie.
5. **Data Flow Analysis Engine** gather information about how values are transmitted through program.
6. **Compiler Construction Toolkits** toolkits including the above programs.

### Little History
- **First electronic computer** in 1940s, programmed using machine code (0s & 1s)
- **Assembly** invented in early 1950s initially as mnemonic representaion of machine instructions, then it was extended with macros.
- Late 1950s saw Fortran, Cobol and Lisp.

### Some Classifications
- **Generations** (first to fourth)
  1. Machine Code
  2. Assembly
  3. High Level Languages (C,C++,Java,Python)
  4. Domain Specific Languages (SQL,NOMAD)
- **Object Oriented Languages** (C++,C#,Java,Ruby)
- **Scripting Languages** (Awk,JavaScript,Perl,PHP,Python,Ruby)
- **Imperative** vs **Declarative**

|             | Defintion                          | Examples          |
| :---------- | :--------------------------------  | :---------------- |
| Imperative  | Describes how a computaion is done | C,C++,Java,Python |
| Declarative | Describes what computation to do   | ML,Haskell        |

[Exercise](exercises/1.3.md)

### Applications Affected By Compiler Technology
#### High Level Programming Languages Implementation
Increasing **abstraction** level, and simulataneously increase **optimization** effeciency (Dataflow optimization)
#### Computer Architectures Optimization
- **Parallelism** at **instruction level** or **processor Level**. 

**Instrcution level** parallelism can be hidden from programmer, where processor executes independant parts in a sequential program in parallel, reordering instructions if needed. Compilers can also reorder instructions. Instruction level parallelism can also be explicit in the instruction set by things like **Very Large Instuction Word** and **SIMD** vector operations.

**Processor level** parallelism refers to having multiple processors that a programmer can explicitly utilize using threads.

- **Memory Heirarchies** Memory hierarchies are a response to the basic limitation that we can build very fast storage or very large storage, but not storage that is both fast and large.

Closer a memory is to the processor, the faster it is. Average memory-access time of a program is reduced if most of its accesses are satisfied by faster levels of the hierarchy.

The performance of a system is often limited not by the speed of the processor but by the performance of the memory subsystem. Compilers traditionally focused on optimizing processor execution, more emphasis is now placed on making the memory hierarchy more effective.

Using registers effectively is probably the single most important problem in optimizing a program. On the other hand caches are hidden from instruction set and managed by hardware, hardware caching policies are in some cases ineffective (with large datasets), so compiler may change structures or code layout to make better use of caches.
#### New Computer Architectures Design
Compiler technologies influence computer architecure design direction and design decision.
- **RISC** became more favored over **CISC**.
- **Specialized Architectures** get proposed to be utilized and evaluated by compiler technologies. Architectures such as:
  - Data Flow Machines
  - SIMD
  - Systolic Arrays
  - Multiprocessors with shared memories
  - Multiprocessors with distributed memory

#### Program Translations
Compiler technologies are used for translating languages, not necessarily from high level to machine code.
- **Binary Translation** (Virtualiztion). Basically converting machine code of an architecture to another.
- **Hardware Synthesis**. Languages like Verilog and VHDL are used to design hardware, where variables represnt registers, and expressions represent combinational logic.
- **Database Query Interpreters** like SQL, may compile queries into native code.
- **Compiled Simulations**. Simulators may compile design descriptions down to machine code, rather than interpreting them, to make simulation faster.

#### Software Productivity Tools
**Static Analyzers** try to detect errors in a program at compile time. They borrow ideas from optimizers inside compilers, the difference being that optimizers are not allowed under any circumastances to change program semantics. Example of important checks are the following:
- **Type Checking**
- **Bounds Checking**
- **Memory Management Tools**

**Up Next:** 1.6 Programming Language Basics (Page 48 in PDF)