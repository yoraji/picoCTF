# Image Processing Web App Exploit

## Description

This challenge involves exploiting a web application that processes **PNG images only**. Your goal is to uncover vulnerabilities and retrieve the flag.

## Solution Steps

1. **Access the Web App**
   - Use `wget` to retrieve the web app link:
     ```bash
     wget http://atlas.picoctf.net:51750/
     ```
   - Navigate to the provided URL and locate the file upload functionality.

2. **Discover Hidden Directories**
   - Use a tool like `gobuster` to find hidden directories:
     ```bash
     gobuster dir -u http://atlas.picoctf.net:51750/ -w /path/to/wordlist
     ```
   - Alternatively, check common paths manually, such as `robots.txt`:
     ```bash
     wget http://atlas.picoctf.net:51750/robots.txt
     ```

3. **Follow Instructions**
   - Locate `/instructions.txt` and follow its guidance to identify vulnerabilities in the app.

4. **Upload a PHP Webshell**
   - Create a PHP webshell disguised as a `.png` file. Ensure it starts with valid PNG headers followed by your PHP payload.
   - Upload the webshell using the app's upload feature.

5. **Access the Uploaded Shell**
   - After a successful upload, visit the shell at:
     ```
     http://atlas.picoctf.net:51750/uploads/your_uploaded_file.png.php
     ```

6. **Retrieve the Flag**
   - Use the shell to navigate the server, locate the flag (likely in the `/root/` directory), and read its contents.

## Notes

- Familiarity with directory brute-forcing, PHP payloads, and basic Linux commands is essential.
- Tools like `gobuster` or `curl` can be helpful for exploration.

**Good Luck!**

