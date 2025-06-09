 An interrupt is a signal sent to the [[FCS-Lec-2#^9b1de0|processor]] indicating that an event requiring immediate attention has occurred. Upon receiving an interrupt, the processor temporarily halts its current execution , saves its state and handles the event(known as servicing the interrupt) before resuming its original task. Interrupts allow computers to respond quickly to critical events and multitask more efficiently.

Interrupts are provided primarily as a way to improve processing efficiency. Suppose that the processor is transferring data to a printer. After each write operation, the processor must pause and remain idle until the printer catches up. The length of this pause may be on the order of many hundreds or even thousands of instruction cycles that do not involve memory. 

# Interrupts and execution cycle

With interrupts, the processor can be engaged in executing other instructions while an I/O operation is in progress. After the few instructions are executed, control returns to the user program. Meanwhile, the external device is busy accepting data from computer memory and printing it. This I/O operation is conducted concurrently with the execution of instructions in the user program.

![[Pasted image 20241020143045.png]] ^facbdd

When the external device sends an interrupt request signal to the processor. the I/O module for that external device sends an *interrupt request* signal to the processor. The processor responds by suspending operation of the current program, branching off to a program to service that particular I/O device, known as interrupt handler, and resuming the original execution after the device is serviced. 

The processor and the operating system are responsible for suspending the user program and then resuming it at the same point.

To accommodate interrupts, an *interrupt cycle* is added to the instruction cycle, as shown in the given figure: 

![[Pasted image 20241020144644.png]]

In the interrupt cycle, the processor checks to see if any interrupts have occurred, indicated by the presence of an interrupt signal. If no interrupts are pending, the processor proceeds to the fetch cycle and and fetches the next instruction of the current program. If no interrupt is pending, the processor does the following:
- It suspends execution of the current program being executed and saves its context(saving the address of the next instruction to be executed) and any other data relevant to the processor's current activity.
- It sets the program counter to the starting address of an *interrupt handler* routine.

# Efficiency of interrupts

The following figures are time diagrams based on the flow of control. 
This is based on the flow of control depicted in [[#^facbdd|Figure 3.7a and 3.7b]]. This figure assumes that the time required for the I/O operation is relatively shorter than the time to complete the execution of instructions between write operations in the user program. 
![[Pasted image 20241020151738.png|500]]

The more typical use case, especially for a slow device such as a printer, is that the I/O operation would take much longer than executing a sequence of user instructions. [[#^facbdd|Figure 3.7c]] indicates this state of affairs. The given figure shows the timing for this situation with and without the use of interrupts.

![[Pasted image 20241022081414.png|500]]

## Multiple Interrupts
There com also be multiple interrupts. There are two approaches to handling multiple interrupts.
- Disable interrupts / sequential interrupts
- Nested Interrupts
### Disable Interrupts/ sequential interrupts
While the interrupt is getting processed all other interrupts are disabled. This means that while the interrupt is getting processed, the processor will ignore all other interrupt requests. After the interrupt handler routine is completed the interrupts are enabled before resuming the user program and the processor checks to see if additional interrupts have occurred.

Drawback: IT does not take into account relative priority and time critical needs.

![[Pasted image 20241022084040.png|500]]

### Nested Interrupts
This involved defining priorities to interrupts and allowing higher priority interrupts to cause a low priority interrupt to itself get interrupted.

![[Pasted image 20241022084643.png|500]]