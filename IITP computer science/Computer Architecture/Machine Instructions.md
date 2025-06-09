## Classified on the basis of type of instructions

### Data transfer instructions:
These instructions move data from one place to another. Eg: $LOAD, \ MOVE , \ IN, \ OUT, \ PUSH, \ STORE$.

#### Data Manipulation instructions: 
These instructions perform Arithmetic, logical and shift operations on data. Eg: $ADD, \ SUB, \ MUL, \ DIV, \ INC, \ AND, \ XOR, \ OR, \ SHR, \ SHL, \ ROR, \ ROL$ 

#### Program control instructions: 
These instructions may change the address value in [[FCS-Lec-2#^2903ba|Program Counter]] and cause the normal sequential flow to change. It changes the way a program is executed.

## On the basis of number of <u>number of address fields</u> 
#### Three-address instruction: 
Specify 2 sources and 1 destination, which can be either a [[FCS-Lec-2#^162ea8|processor]] register or a memory operand. It results in a short program but required too many bits to specify three addresses. 
Eg: $ADD \ R_{1}, \ A, \ B$ is the same as $R_{1}\leftarrow M[A] + M[B]$ 
*$M[A]$ and $M[B]$ mean memory addressing the specific values from memory*
#### Two-address instruction:
Each address field can specify either a [[Brief History Of Computers|processor register]] or a memory word.
Eg: 
- MOV $R_{1}$, A means $R_{1}\leftarrow \ M[A]$ 
- MUL $R_{1}, \ R_{2}$ translates to $R_{1}\leftarrow R_{1}\times R_{2}$ 
#### One-address instruction: 
It uses an implied [[Brief History Of Computers#^2903ba|accumulator(AC)]] register for all data manipulation. The other operand is in register or memory.
Eg: 
- LOAD $A$ (AC $\leftarrow \ M[A]$)
- ADD $B$ (AC $\leftarrow \ M[B]$)
#### Zero-address instruction:
A stack organized computer does not use an address field for the instruction $ADD$ and $MUL$.