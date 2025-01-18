# Heap Overflow Challenge

## Description

Can you control your overflow?  
Your goal is to exploit a heap overflow vulnerability to retrieve the flag.

- [Download the binary](https://artifacts.picoctf.net/c_tethys/32/chall)  
- [Download the source](https://artifacts.picoctf.net/c_tethys/32/chall.c)  

Additional details will be provided after launching your challenge instance.

## Solution Steps

1. **Download the Source Code**
   - Retrieve the source file for analysis:
     ```bash
     wget https://artifacts.picoctf.net/c_tethys/32/chall.c -O chall.c
     ```

2. **Analyze the Code**
   - Examine the code to understand the conditions required for triggering the overflow.  
     Key observation: There is a 32-byte buffer, and any input exceeding this length can overflow the heap.

3. **Craft the Overflow Payload**
   - Construct an input string that fills the buffer and satisfies the condition to access the flag. For example:
     ```
     12345678901234567890123456789012pico
     ```
   - The string must overflow the buffer and include the keyword `pico` at the end to pass a specific condition in the code.

4. **Execute the Exploit**
   - Run the binary, provide the crafted input, and trigger the overflow:
     ```bash
     ./chall
     ```
   - If successful, the flag will be printed.

5. **Retrieve the Flag**
   - The flag format is typically `picoCTF{...}`. For example:
     ```
     picoCTF{starting_to_get_the_hang_e9fbcea5}
     ```

## Notes

- Understanding how heap overflow works and analyzing the source code are crucial.
- This challenge is a great introduction to memory corruption and heap-based exploits.

**Good Luck!**

