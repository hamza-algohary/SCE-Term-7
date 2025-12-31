### 1. Example for simple bus-based datapath

![](../media/lecture7/simple-bus-based-datapath.png)

- Function unit is composed of ALU & Shifter.
- Inputs 
  - $A$ & $B$ are represented as MUXs
  - ALU takes $A$ & $B$, while shifter takes $A$ only.
  - $B$ might be a register or a constant.
  - $A$ might be a memory address. $B$ may be written to memory.
- Output 
  - might be from ALU, Shifter, Memory. 
  - Only ONE register may be loaded at a time.
  - $\bold{load enable}$ signal may disable loading completely.

The group of signals driving all that is called a **Control Word**.  
![](../media/lecture7/control-word-example.png)

### 2. Specify the control word to perform the following microoperation: $R1←R2 +R3$
**Solution**  
- AA = 10
- BA = 11 
- MB = 0
- G = ADD code
- MF = 0
- MD = 0
- Destination select = 01
- Load enable = 1

### 3. ALU Detailed Example
ALU's interface could be
- **Inputs:** Operands $A$ & $B$ and operation selectors $S0$, $S1$, $S2$, $Cin$.
- **Outputs:** Output $G$ Carry Out $Cout$

ALU's internals could be the following
$S2$ determines arithemtic or logic operation.  
For arithmetic operations
- $S0$ & $S1$ makes second operand one of
  - all 0s
  - $B$
  - $\overline{B}$
  - all 1s
- $Cin$ just gets fed to the adder

| Operation           | Selectors (S1 S0 Cin) | Result             |
| :------------------ | :-------------------- | :----------------- |
| Add                 | **010**               | $A+B$              |
| Subtract            | **101**               | $A+\overline{B}+1$ |
| Increment           | **001**               | $A+1$              |
| Decrement           | **110**               | $A-1$              |
| Transfer (+0 or -0) | **000** or **111**    | $A$                |

[Full Table](../media/lecture7/arithmetic-circuit-table.png)

The [arithmetic circuit](../media/lecture7/arithmetic-circuit.png) is just a full adder, whose second operand is tampered with based on operation select.

For [Logic Operations](../media/lecture7/alu-logic-operations-diagram.png) we may use just $S0$,$S1$ to select **AND**,**OR**,**NOT** or **XOR**



### 4. Design a parallel adder
**Full Adder Circuit**  
$S = A ⊕ B ⊕ Cin$  
$Cout = (A ⋅ B) + (Cin ⋅ (A ⊕ B))$

- $G_i = A_i ⊕ B_i → \text{Carry Generate}$  
- $P_i = A_i.B_i  → \text{Carry Propagate (ie:make Cout=Cin)}$  
- $S_i = \text{partial sum} ⊕ C_{i}$  
- $C_{i+1} = “G_i || P_i”$  

Where $G_i$ is always the same for all stages, while $P_i$ is squashed into two layers only at each stage because it depends on previous carry (logically)