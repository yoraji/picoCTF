# Description

Can you abuse the banner?

The server has been leaking crucial information on `tethys.picoctf.net` at port 61060. Use the leaked information to gain access to the server.

To connect to the running application, use the command:
From the leaked information, exploit the machine and find the flag in the `/root` directory.

---
nc tethys.picoctf.net 54451

From the leaked information, exploit the machine and find the flag in the `/root` directory.

---

# Solution

1. First, run the following command:
    ```
    nc tethys.picoctf.net 61060
    ```
    You'll receive a password: `My_Passw@rd_@1234`.

2. Next, run the command:
    ```
    nc tethys.picoctf.net 50878
    ```
    Submit the password, and you’ll be asked a series of questions. You can easily find the answers by searching on Google.

3. Once you’ve answered the questions, use the shell code to move the content of `script.py` to the current directory. Name it `banner`, but be sure to keep the original file.

4. Run the following command again:
    ```
    nc tethys.picoctf.net 50878
    ```
    Congratulations! You will now receive the flag.

Good luck!

---

