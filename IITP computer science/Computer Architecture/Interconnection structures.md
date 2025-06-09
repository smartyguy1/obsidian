A computer is a network of basic modules. The collections of paths connecting the various modules is called the interconnection structure.

![[Pasted image 20241022085311.png|400]]

# Bus interconnection

A bus is a communication Pathway connecting two or more devices. It is a shared transmission medium. Multiple devices connect to the bus, a signal transmitted by one device is available for revert portion by all other devices attached to the bus.

A bus that connects make computer components is called the System bus.
## Bus structure
A bus is a communication pathway connecting two or more devices. 
- It is a shared transmission medium. 
- Multiple devices connect to the bus, and a signal transmitted by any one device is available for reception by all other devices attached to the bus.
- A system bus typically consists of from about 50 to hundreds of separate lines. Each line is assigned a particular meaning or function

![[PNG image 1.png]]

- The **data lines** provide a path for moving data among system modules. These lines are called the data bus
- The **address lines** are used to designate the source or destination of the data on the data itself.
- The **control lines** are used to control the access to and the use of the data and address lines.

Since these are shared buses. So, If more devices are attached:
- Length of bus increases and hence the propagation delay
- The bus may become a bottle neck as the aggregate data transfer demand, approach the capacity of the bus.
These drawbacks can be mitigated by increasing bus width and data rate. But data rates of attached devices are growing steadily.

## Multiple Bus Hierarchies
### Traditional Bus Architecture

- To connect various I/O controllers, we can make use of multiple expansion buses for this purpose. 
- An **expansion bus interface** *buffers* data transfers between the system bus and the I/O controllers on the expansion bus.
- This arrangement allows the system to support a wide variety of I/O devices and at the same time insulate memory-to-processor traffic from I/O traffic. 

![[PNG image 2.png]]

This architecture is reasonably efficient but begins to break down as higher and higher performance is seen in I/O devices.
### Mezzanine Architecture

- A high performance bus that is closely integrated with the rest of the system, requiring only a bridge between the processor's bus and the high-speed bus. 
- There is a local bus that that connects the processor to a cache controller, which is in turn connected to a system bus that supports the main memory.
- The advantage of this arrangement is that the high-speed bus brings high demand devices into closer integration with the processor and at the same time is independent of the processor. Changes in processor architecture do no affect the high-speed bus, and vice versa.

![[PNG image 3.png]]

### Point-to-Point interconnect
![[IMG_0039.jpeg]]

- Principal reason for change was the electrical constraints encountered with increasing the frequency of wide synchronous buses.

- At higher and higher data rates, it becomes increasingly difficult to perform the synchronisation and arbitration function in a timely fashion.

- A conventional shared bus on the same chip magnified the difficulties of increasing bus data rate and reducing bus latency to keep up with the processor.

Point-to-Point interconnection has lower latency, high data rate and better scalability.

#### Peripheral Component Interconnect (PCI)

- A popular high bandwidth, processor independent bus that can function as a mezzanine or peripheral bus

- Delivers better system performance for high speed I/O subsystems

- **PCI Special Interest Group**: Created to develop further and maintain the compatibility of the PCI applications

- **PCI Express(PCIs)**: Point-to-point interconnect scheme intended to replace bus based schemes such as PCI.
	- Key requirement is high capacity to support the needs of higher data rate I/O devices such as Gigabit Ethernet
	
	- Another requirement deals with the need to support time dependent data schemes.