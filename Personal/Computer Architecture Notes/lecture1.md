
**Computer Architecture** includes the study of functional blocks that make up the computer system and the way they are connected.

**Computer Organization:** concerned with the implementation of computer architecture, and involves # processors, memory size, time to execute an instruction,….etc.

**Computer engineering**: referred to the actual construction of a computer. 

### Von-Neumann Architecture
- A computer 
    - consists of **CPU**, **Memory**, and **IO**
    - is independent of the problem 
- Memory
    - is divided into cells of equal size
    - Instructions and Data are stored in the same memory
- A program
    - is a sequence of instructions
    - data and instructions are represented by binary signals

### CPU Components
1. **Control Unit**
    - Controls all other units and controls the flow of data from one unit to another for performing computations. 
    - Also sequences the operations of all the units with the help of clock pulses.

2. **Operation Unit (ALU)** is used for performing arithmetic and logic operations.

### Means of Communications between CPU and Memory or IO Devices
1. **Address Bus** 
    - A unidirectional bus used by the CPU to select a memory location or IO port.
    - Number of bits in the address bus determines the maximum number of bytes of data in the memory that can be accessed

2. **Data Bus**
    - It's bidrectional.
    - A microprocessor is characterized by the width of its data bus.
    - Its size determines the largest number that can be processed by a microprocessor (also called a Word).

3. **Control Bus** synchronizes different components, and determines operation (read or write) so it's along side **Address Bus**.



### Parallelism 
Levels of parallelism
1. **Data-Level Parallelism** Many data items can be operated on at the same time.
2. **Task-Level Parallelism** Tasks of work created that can operate independently and largely in parallel.

Michael Flynn’s Classifications
1. **SISD** Single Intruction stream Single Data stream
2. **SIMD** Single Intruction stream Multiple Data stream
3. **MISD** Multiple Intruction stream Single Data stream
4. **MIMD** Mutiple Intruction stream Mutiple Data stream

### Locality
Programs tend to reuse data and instructions they have used recently.

A widely held rule of thumb is that a program spends 90% of its execution time in only 10% of the code.

An implication of locality is that we can predict with reasonable accuracy what instructions and data a program will use in the near future based on its accesses in the recent past.

Types of locality
1. **Temporal Locality** Recently accessed items are likely to be accessed in the near future.
2. **Spacial Locality** Near addresses tend to be referenced close together in time.

A principle in computer design is to favor the frequent case over the infrequent case.

### Quantitative Principles of Computer Design
**Amdhal's Law** Performance gain from using some faster mode of execution is limited by the fraction of the time the faster mode can be used.

Overall Speed Up depends on two factors:
1. **Fraction Enhancement:** Fraction of the original computation time that takes advantage of the enhancement.
2. **Speedup Enhancement** improvement gained by the enhanced execution mode for the optimized portion of the program

$ Overall Speedup = \dfrac{Execution Time}{Execution Time After Enhancement} = \dfrac{1}{(1-Fraction Enhancement)+\dfrac{Fraction Enhancement}{Speedup Enhancement}} $

CPU Time = #instructions × Average Cycles per Instruction × Clock Cycle Time

Benchmarks Types
1. **Natural** Real programs used to solve a real task
2. **Synthetic** Sequence of instructions constructed for the purpose of measuring performance.

Dependability Measures
1. **Module Reliability**
    - **MTTF** Mean Time To Failure
    - **λ** Rate of failures = **1/MTTF**
    - **MTTR** Mean Time To Repair
    - **MTBF** Mean Time Between Failures = **MTTF + MTTR**  
2. **Module Availability** = $ \dfrac{MTTF}{MTTR} $

--------------------------------------------------------------------

#### Assesment: Give a brief about:
1. “HARVARD Computer Architecture”.
2. Data Flow computers

#### Sheet
Examples at pages: 34 , 47, and 50 from Hennessy ‘s book.