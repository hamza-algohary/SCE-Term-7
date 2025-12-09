# Register Transfers
A **register** is a set of flip flop + optional combinational gates.

A **counter** is a register that goes through a predetermined sequence of states  on each clock.

### Latches
A latch is a storage unit.
- [SR latch](media/lecture6/sr-latch.png)
- [SR latch with control](media/lecture6/sr_with_control.png)
- [D latch](media/lecture6/d-latch.png)

### Flip Flops
A flip flop is a storage unit that operates with a clock.
- [Master Slave SR](media/lecture6/master-slave-sr-flip-flop.png)
- [Positive Edge Triggered Flip Flops](media/lecture6/positive-edge-flip-flop.png), and [Negative](media/lecture6/negative-edge-flip-flop.png) as well.

### Sequential Circuit Design
**Output** & **Next State** are functions in **Input** & **Previous State**.

Steps:
1. **Specification**
2. **Formulation**: state diagram or table.
3. **State Assignment:** assign every state a binary code.
4. **Flip Flop Input Equations**
5. **Output Equations**
6. **Optimization**
7. **Logic Diagram**
8. **Verification**


**Parallel Load** is when a register loads all its bits simultaneously on each clock. [Diagram](media/lecture6/parallel-load-register.png)

A digital system (sequential circuit) is specified by a state table. However, for large systems the number of states is very large and impossible to put in a state table. Therefore, we use modular hierarchical design approach instead.

Most digital systems are divided into:
1. **Datapath** (ALU) defined by registers and operations.
2. **Control Unit** that determines sequence of operations.

**Register Transfer Operations** refer to movement and processing of data on registers. They are specified by
1. Set of registers
2. Operations
3. Control entity to supervise sequence of operations

**Microoperations** are elementary operations performed on all bits of a register in parallel in one clock cycle, like:
1. Transfer
2. Arithemtic
3. Logic
4. Shift

### Register Transfer Language (RTL)
A language to describe datapaths, by describing operations on registers and assigning them to control signals.

**Notation**
| Symbol             | Meaning                        | Example                   |
| :----------------- | :----------------------------- | :------------------------ |
| Letters & Numerals | Registers                      | `AR` `R2`                 |
| Parantheses        | Part of register               | `R2(1)` `R2(7:0)` `AR(L)` |
| Arrow $\leftarrow$ | data transfer                  | `R1 <- R2`                |
| Commma             | Separate simultaneous transfer | `R1 <- R2  , R2 <- R1`    |
| Square Brackets    | Memory Address                 | `R0 <- M[R1]`             |
| `if (condition) then (action)` <br> or simply `condition:action` | Conditional Statement | `if (k1=1) then (R2<-R1)` or `K1:R2 <- R1` |

**Operators** 
- `=` **Assignment**
- `←` **Register Transfer**
- `+` `-` **Plus** & **Minus**
- `^` `∨` `⊕` <sup>`¬`</sup> Bitwise **AND**, **OR**, **XOR** and **NOT**
- `sl` `sr` Logical **shift left** and **right**
- `||` **Concatenation**

Shift is used in serial transfer of data, and for manipulating the contents of registers in arithmetic, logical, and control operations.

**Transfer**
- **Multiplxer Based**  Each source has a multiplexer. Control signal selects source.[example](examples/lecture6.md#4-multiplexer-based-transfer).
- **Bus Based** A bus is a set of common lines. Control signal selects a single source and multiple destinations. [example](examples/lecture6.md#5-bus-based-transfer)
  - **Three State Bus** tri-state buffers have one level of logic gates wherease a MUX has two. Allows bidirectional signal transfer into and out of a circuit from one interconnection. [Example](media/lecture6/tri-state-bus.png)
- **Memory Transfer** 
  - **Read** `DR ← M [AR]` Content of `AR` is sent to address decoder, and data destination decoder sends load signal to `DR`.
  - **Write** `M [AR] ← DR` Content of `AR` is sent to address decoder, data source decoder will send an enable signal to `DR`.

