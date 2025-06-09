# Bitwise Operators
`a = 60` $(a)_2 = 0011 \ 1100$
`b = 13` $(b)_2 = 0000 \ 1101$ 

| Operator | Description                                                                                                              | Example                                   |
| -------- | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------- |
| `&`      | Binary AND Operator. Copies a bit if it exists in both operands                                                          | `a & b` will give 12 which is 0000 1100   |
| \|       | Binary OR Operator. Copies a bit if it exists in both operands                                                           | `a\|b` will give 61 which is 00l11 1101   |
| `^`      | Binary XOR Operator. Copies the bit if it is set in one operand but not both                                             |                                           |
| `~`      | Binary Ones Complement Operator is unary and has the effect of 'flipping'  bits                                          | `(~a)` will give $-61$ which is 1111 0010 |
| `<<`     | Binary Left Shift Operator. The left operands value is moved left by the number of bits specified by the right operand   | `a << 2` will give 240 which is 1111 0000 |
| `>>`     | Binary Right Shift Operator. The left operands value is moved right by the number of bits specified by the right operand | `a>>2` will give 15 which is 0000 1111    |

# Assignment Operators

| Operator | Description                                                                                                            | Example                              |
| -------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| `=`      | Simple assignment operator, assigns values from the right side operands to left side operand                           | `c = a + b`                          |
| `+=`     | Add and assignment. It adds right operand to the left operand and assigns the result to the left operand               | `c+=a` is equivalent to `c = c+ a`   |
| `-=`     | Subtract and assignment. It subtracts right operand to the left operand and assigns the result to the left operand     | `c-=a` is equivalent to `c = c-a`    |
| `*=`     | Multiply and assignment. It multiplies right operand to the left operand and assigns the result to the left operand    | `c*=a` is equivalent to `c = c*a`    |
| `/=`     | Divide and assignment. It divides right operand to the left operand and assigns the result to the left operand         | `c/=a` is equivalent to `c = c/a`    |
| `%=`     | Modulus and assignment operator. It takes the modulus using two operands and assign the result to the left operand     | ` c %= a` is equivalent to `c = c%a` |
| `**=`    | Exponent and assignment. Exponentiates the left operand by the right operand and assigns the value to the left operand | `c**=a` is equivalent to `c=c%a`     |
| `//=`    | Floor division and assigns a value, perform floor division on operators and assign value to the left operand           | `c //=a` is equivalent to `c = c//a` |
