
# Types of Digital Systems

1. **No state present or combinational logic system**: No role of history, the output depends solely on the current inputs and not on any previous inputs or outputs.
	- Output $=f(x)=\text{Function}(input)$ 

2. **State Present or Sequential System**: A **sequential system** in digital electronics is a system where the output depends not only on the current input but also on the history of past inputs
	1. **Synchronous Sequential System**: These systems change state only at specific times, typically on the rising or falling edge of a clock signal
	
	2. **Asynchronous Sequential System**: These systems do not rely on a clock signal for state changes; instead, they respond immediately to changes in inputs
		- State is updated at any time
		- $\text{State}=\text{function}(\text{State, Input})$ 
		- $\text{Output} = \text{function}(\text{State, Input})$ 

#### Example: A digital counter(eg: odometer)

The value in an odometer is going to depend on how fast the car is going. It will increment by a lot if the car is going very fast, by a small unit if the car is slow and not at all if the car remains at rest.

# Signal
- An information variable represented by a physical quantity
- For digital systems, the variable takes on discrete values
- Binary values are most prevalent values in digital systems
- Binary values are represented abstractly by:
	- Digits 0 & 1
	- Words(symbols) False(F) and True(T)
	- Words(Symbols) Low(L) and High(H)
	- Words On & Off
- Binary values are represented by the values or range of values of physical quantities.

# Number Systems
- Positive Radix and positional number systems
- A no. with radix $r$ is represented by a string of digits: $A_{n-1}A_{n-2}\dots A_{1}A_{0}.A_{-1}A_{-2}\dots A_{-m+1}A_{-m}$  in which $0\leq A_{i} \leq r$ and $.$ is the *radix point*.
- The string of digits represents the power series: $$
\text{(Number)}_{r}= \sum\limits_{i=0}^{i=n-1}{A_{i}\cdot r^{i}} \ + \sum\limits_{j=-m}^{j=-1}{A_{j}\cdot r^{j}}
$$
