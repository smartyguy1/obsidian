
Contemporary computer designs are based concepts developed by **John von Neuman** at the **Institute for Advanced Studies, Princeton**.

Referred to as the *[[Von Neuman's Earlier Proposal|von Neuman Architecture]]* and is based on three key concepts:
- Data and instructions are stored in a single read-write memory
- The contents of this memory are addressable by location, without regard to the type of data contained there.
- Execution occurs in a sequential fashion (unless explicitly modified) from one instruction to the next.
There is a small set of logic components that can be combined in various ways to store binary data and perform arithmetic and logical operations on that data. If there is a particular computation to be performed, a configuration of logic components designed specifically for that computation could be constructed. 
##### Hardwired Program
We can think of this process as a form of programming . The resulting program is in the form of hardware and termed a *hardwired program*.
### Software:

![[Pasted image 20240907144747.png]] ^ef5349

- Consider the alternative of a *Hardwired Program* where we have a general purpose configuration of Arithmetic and logic functions. This set of hardware will perform various functions on data depending on control signals applied to the hardware. This way instead of rewiring the hardware, the *programmer* simply needs to supply a new set of control signals.

- In such a program, a unique code is used for each possible set of control signals. Let us provide a unique code for each possible set of control signals, and let us add to the general-purpose hardware a segment that can accept a code and generate control signals.
#### Major Components
- **CPU**:  ^eec64b
	- Instruction interpreter
	- Module of general-purpose arithmetic and logic functions
	- **[[FCS-Lec-2#^d4bb90|Structural Components of a CPU]]**
- **I/O Components:** ^38dc9a
	- Input Module:
		- Contains basic components for accepting data and instructions and converting them into an internal form of signals usable by the system
	- Output module:
		- Means of reporting results
- **Memory or main memory module**:
	- A place to store temporarily both instructions and data.

Consider [[#^ef5349|this]] illustration of the top level components and their interactions.

- The CPU exchanges data with memory. For this purpose it uses two registers (inside CPU):
	- [[Brief History Of Computers#^228fe9|MAR]]- Specifies the the address in memory for the next read or write
	- [[Brief History Of Computers#^228fe9|MBR]] - Contains the data to be written into memory or receives the data read from the memory.
	- **I/O address register (I/OAR)**: Specifies a particular I/O device.
	- **I/O Buffer Register(I/OBR):** Used for Exchange of data between an [[#^38dc9a|I/O module]] and the [[#^eec64b|CPU]].

