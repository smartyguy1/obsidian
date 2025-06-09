
## The First Generation: Vacuum Tubes
- Vacuum tubes were used for digital boys element and memory
- **ENIAC**: Electronic Numerical Integrator And Computer, designed and constructed at the University of Pennsylvania was the world's first general-purpose electronic digital computer
### The Von Neuman Machine

^bd8ac9

- Based on the idea of *stored-program concept*.
- It is referred to as the IAS computer
    - fundamental design approach was the **stored program concept**.
        - attributed to the mathematician John Von Neumann.
        - first publication of the idea was in 1945 for the EDVAC.
- Design began at the Princeton Institute for advanced studies.
- Completed in 1952
- Prototype of all subsequent general-purpose computers.

General structure of the IAS computer; it consists of-
- A main memory, which stores both data and instructions
- An arithmetic and Logic unit (ALU) capable of operating on binary data
- A Control Unit, which interprets the instructions in memory and causes them to be executed.
- Input and Output(I/O) equipment operated by the control unit

#### IAS Memory Structure
- The memory consists of a 1000 storage locations, called *words* of 40 binary digits(bits) each. 
- Numbers are represented in binary form and each instruction is a binary code
- A *word* may contain two 20-bit instructions, with each instruction consisting of an 8-bit operation code (*opcode*) specifying the operation to be performed and a 12-bit address designating one of the words in memory.
- The [[FCS-Lec-2#^58a908|control unit]] operates the IAS by fetching instructions from memory and executing them one at a time.

![[Pasted image 20241015075137.png]]

####
Both the [[FCS-Lec-2#^58a908|Control Unit]] and [[FCS-Lec-2#^442146|ALU]] contain storage locations called *registers* defined as follows:-

- **Program Counter(PC)** It keeps track of the <u>memory address of the next instruction to be executed in a program</u>.

- **Memory Address Register (MAR)**: It specifies the address in memory of the words to be written from or read into the MBR.

- **Memory Buffer Register(MBR)**: It contains a <u>word to be stored in memory or sent to the I/O unit</u>. Or it is used to receive a word from memory or from the I/O unit. Its size is 40 bits.

- **Accumulator (AC) and Multiplier Quotient(MQ)**: employed to temporarily hold operands and results of ALU operations. ^2903ba

- **Instruction Register(IR)**: Contains the 8-bit opcode instruction being executed.

- **Instruction Buffer Register(IBR):** Employed to hold temporarily the right-hand instruction from a word in memory. ^228fe9

The IAS operates by repetitively performing an *instruction cycle*. Each instruction cycle consists of two subcycles.

![[PNG image.png]]

#### IAS Operation

![[2AE2F03B-CAE5-49E2-A5E6-77824F20E322.png]]

The IAS computer has a total of 21 [[Machine Instructions|instructions]] that can be grouped as:
- **Data Transfer**: Move data between memory and ALU registers or between two ALU registers
- **Unconditional Branch**: Normally, the control unit executes instructions in sequence from memory. This sequence can be changed by a branch instruction, which facilitates repetitive operations.
- **Conditional Branch:** The branch can be made dependent on a condition, thus allowing decision points.
- **Arithmetic**: Operations performed by the [[FCS-Lec-2#^442146|ALU]] 
- **Address modify**: Permits addresses to be computed in the ALU and then inserted into instructions stored in memory. This allows a program considerable addressing flexibility. 

## 2nd Generation(Transistors)

- Vacuum tubes were replaced by transistors which were more reliable and efficient. This led to reduction in the size of the computers, improved speed and lowered energy consumption.
- Assembly language was still used, but more sophisticated compilers and high-level languages allowed for more complex applications.
## 3rd Generation(Integrated Circuits or ICs)

- Integrated Circuits replaces transistors, allowing for even smaller and faster computers. ICs incorporated multiple transistors into a single silicon chip, drastically increasing computation power while reducing cost and size.
- The development of more advanced high level languages such as BASIC and the ride of time-sharing systems
## 4th Generation (Microprocessors)

- The invention of the Microprocessor (a single chip that could handle all the functions of a computer's CPU) revolutionized computing. This generation saw the development of personal computers
- More user-friendly operating  systems emerged, and programming languages such as C and later C++ became widespread.

## 5th Generation(Artificial Intelligence and Beyond)

- The fifth gen focuses on AI, machine learning and quantum computing. Advanced technologies such as parallel processing, neural networks, and sophisticated algorithms are enabling computers to process large datasets and solve complex problems more efficiently
- AI-focused languages like Python and specialized tools for machine learning and data science dominate this generation.