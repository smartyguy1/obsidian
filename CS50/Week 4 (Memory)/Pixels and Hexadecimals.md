# Pixel Art
- Pixels are squares, dots, of color that are arranged on an up-down, left-right grid.
- We can imagine an image as a map of bits, where zeros represent black and ones represent white.
![[Pasted image 20240720154225.png]]

- RGB(or *red*, *green* and *blue*) are numbers that represent the amount of each of these colors. In Adobe Photoshop, you can see these settings as follows:
![[Pasted image 20240720154351.png|500]]
	Notice how the amount of red, blue and green changes the color selected
- You can see by the image above that color is not just represented in three values. At the bottom of the window, there is a special value made up of numbers and characters. `255` is represented as `FF` (Hexadecimal) ^7ca7c9

# Hexadecimal

^c11312

- System of counting that has 16 counting values. They are as follows:
```
0 1 2 3 4 5 6 7 8 9 a b c d e f
```
Notice that `F`(doesn't matter whether lower-case or upper they are recognized just the same) represent `15`
- Hexadecimal is also known as *base-16*
- When counting in hexadecimal, each column is a power of 16
- The number `0` is represented as `00`.
- The number `1` is represented as `01`
- The number `9` is represented as `09`
- The number `10` is represented as `0A`
- The number `15` is represented as `0F`
- The number `255` is represented as `FF`, because $16\times15$ (or `F`) is 240. Add $16^{0}\times 15$ (or `F`) we get, [[#^7ca7c9|255]]. This is the highest number you can count using the 2-digit hexadecimal system.
- Hexadecimal is useful because it can be represented using fewer digits. Hexadecimal allows us to represent information more succinctly.
![[Pasted image 20240720160323.png|400]]
- Hexadecimals make this mapping easy because a group of 4 binary digits(bits) has **16** different combinations, and each of those combinations maps to a single hexadecimal digit. 
- Hexadecimals are represented as `0x` just so we can identify it as a hexadecimal. so $2346$ in hexadecimal is `0x92A`. 
## Binary to Hexadecimal

- To convert a binary number to hexadecimal, group 4 binary digits(bits) together from right to left.
	- Pad the leftmost group with extra 0 bits at the front **if necessary**.
- Then use the chart to convert those bits to something more concise.
![[Pasted image 20240720162247.png]]

### Example:
`01000110101000101011100100111101` To convert this to hexadecimal:

`01000110101000101011100100111101`$\rightarrow$ `0100 0110 1010 0010 1011 1001 0011 1101`

![[Pasted image 20240720162530.png|300]] 
Then, 
![[Pasted image 20240720162653.png|300]]

On repeating this process we get:
![[Pasted image 20240720162724.png|300]]

So the hexadecimal is `0x46A2B93D`