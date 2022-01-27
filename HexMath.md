# Flags

**Carry flag (CF):** 

**Exceed unsigned range!**
Set if arithmetic operation generates a carry or borrow out of the MSB

It is the **overflow** flag for unsigned arithmetic. 

0xFF + 1 = 0x100 -- sets carry
0x05 - 0x06 = 0xFF -- also sets carry, (i.e. generates borrow)
0x05 - 0x04 = 0x01 -- does **not** set carry 

Question: This looks almost like if you had an 'extra bit' to the left of the MSB. 
For example, 0xFF + 0x01 = 0x100, it's as if we have one extra bit to the left of the MSB. Even though that bit isn't actually present in the processor (as far as I know). Because we had this imaginary bit set, we have to set the carry flag. 


So would it be useful to think of it that way? 

**Zero Flag**
Set if result is **zero**, **cleared** otherwise. 
We only worry about the *register*, not what's outside it. 
i.e. if we have 0b 1111 1111 + 0b1 = 0b0000 0000 we set ZF, CF

**Sign Flag (SF)**
Set equal to the MSB of the result. 

**Overflow Flag (OF)**

**Exceed the signed range**
Set if the result overflows into the sign bit.
- Too large of a positive number
- Too small of a negative number
Set when:
Two positive operands generate a negative sum.
Two negative operands generate a positive sum. 
Question: is this only when dealing with signed numbers?
No, it's set regardless. 

Example:
char x = 0x7f; (x=127)

x = x+1; now x == 0x80 (128)

0x80 = -128 in signed arithmetic, thus the overflow flag is set. 

When we have reached an 'impossible value' from normal arithmetic, using signed numbers, the overflow flag is set. 


