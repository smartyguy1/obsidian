![[Pasted image 20240924133636.png|600]]

The basic function performed by a computer is execution of a program, which consists of a set of instructions stored in memory. The processor does the actual work by executing instructions stored in memory. 

## Instruction processing:
-  The processor reads/*fetches* instructions from memory one at a time and executes each instruction.
	1. Program Execution consists of repeating the process of instruction fetch and instruction execution. 
-  The processing required for a single instruction is called an *instruction cycle* 
- The two steps are referred to as the *fetch cycle* and the *execute cycle*.
- Program execution halts only if the machine is turned off, some sort of unrecoverable error occurs, or a program instruction that halts the computer is encountered. 
### Instruction Fetch and execute 

![[Pasted image 20240924135609.png]]

- The processor fetches an instruction from memory. In a typical processor, a register called the [[Brief History Of Computers#^228fe9|program counter(PC)]] holds the address of the instruction to be fetched next. 
- Unless told otherwise, the processor always increments the PC after each instruction fetch so that it will fetch the next instruction in sequence (i.e. the instruction located at the next higher memory address)
- The fetched instruction is loaded into a register in the process known as the [[Brief History Of Computers#^228fe9|instruction register(IR)]].
- The instruction contains bits that specify the action the processor is to take. The processor interprets the instruction and performs the required action. 

The processor interprets the instruction and performs the required action. In general, these actions fall into four categories:

- **Processor-memory**: Data transfer from processor to memory or from memory to processor
- **Processor-I/O**: Data transfer to or from a peripheral device by transferring between the processor and an I/O module
- **Data Processing**: The processor may perform some arithmetic or logical operations on the data
- **Control**: An instruction may specify that the sequence of execution be altered.
It is convenient to organize memory using 16-bit words. The instruction format provides 4 bits for the **opcode**(operation code), so that there can be as many as $2^{4}= 16$ different opcodes and up to $2^{12}= 4096$ words of memory can be directly addressed.

## A detailed look at the basic instruction cycle

The execution cycle for a particular instruction may involve more than one reference to memory. Also, instead of memory references, an instruction may specify an I/O operation.
For any given instruction cycle, some states may be `NULL` and others may be visited more than once. 
The states can be described as:
- **Instruction address calculation (iac)**: Read instruction from its memory location into the processor
- **Instruction Operation Decoding(iod)**: Analyze instruction to determine type of operation to be performed and operand(s) to be used.
- **Operand Address Calculation(oac)**: If the operation involves reference to an operand in memory or available via I/O, then determine the address of the operand.
- **Operand fetch(of)**: Fetch the operand from memory or read it in from I/O.
- **Data Operation(do)**: Perform the operation indicated in the instruction.
- **Operand store(os)**: Write the result into memory or out to I/O.

![[Pasted image 20241015084946.png]]

The *oac* state appears twice, because an instruction may involve a read, a write or both. However, the action performed during that state is fundamentally the same in both cases, and so only a single state identifier is needed.

On some machines, a single instruction can specify an operation to be performed on a vector (one-dimensional array) of numbers or a string(one-dimensional array of characters). As the above figure indicates, this would involve repetitive operand fetch and/or store operations.

