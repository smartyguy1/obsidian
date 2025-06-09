With the constraints of binary numbers, we can assign any binary combination(called a code word) to any data as long as data is uniquely encoded.

# Information Types
### Numeric:
- Most represent range of data needed
- Very desirable to represent data such that simple, straight forward computation for common arithmetic operations are permitted.
- Tight relation to binary numbers

### Non-Numeric
- Greater flexibility since arithmetic operations are not applied 
- Not tied to binary numbers
#### Non-Numeric Binary codes:

- Given $n$ binary digits (called bits), a binary code is a mapping from a set of represented elements to a subset of the $2^{n}$ binary elements.

- For eg: Binary code for the seven colors of the rainbow:

| Colour | Binary code |
| ------ | ----------- |
| Red    | 000         |
| Yellow | 001         |
| Orange | 010         |
| Green  | 011         |
| Blue   | 100         |
| Indigo | 101         |
| Violet | 110         |
Code 111 is not used

# Number of bits required

Given $M$ elements to be represented by a binary code. The minimum number of bits $n$, needed satisfies the following relationship:
$2^{n}\geq M > 2^{n-1}$, $n=\lceil\log_{2}{M}\rceil$, where $\lceil\cdot\rceil$ is called the *ceiling function*(get the smallest integer greater than or equal to the given number).

## Number of elements represented
Given $n$ digits in radix $r$, there are $r^{n}$ distinct elements that can be represented.
