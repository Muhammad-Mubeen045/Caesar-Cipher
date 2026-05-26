🔐 Caesar Cipher Tool
A feature-rich C++ command-line application for text encryption and decryption using the Caesar Cipher algorithm. Includes file operations, brute-force cracking, random key generation, and a custom wordlist generator.

📋 Table of Contents
    • Features
    • Getting Started
    • Usage
    • Menu Options
    • Example
    • Project Structure
    • Notes

✨ Features
    • Encrypt / Decrypt text with a custom shift key (1–25)
    • Brute Force all 25 possible Caesar cipher decryptions
    • Random Key encryption and decryption
    • File Encryption / Decryption — encrypt or decrypt entire text files
    • Key File Generator — save a randomly generated key to a file
    • Custom Wordlist Generator — generate password wordlists from personal info

🚀 Getting Started
Prerequisites
    • A C++ compiler (g++, clang++, MSVC, etc.)
Compile
g++ -o caesar_cipher main.cpp
Run
./caesar_cipher
On Windows:
caesar_cipher.exe

🖥️ Usage
When launched, the program displays an interactive menu:
====== Caesar Cipher Tool ======
1.  Encrypt
2.  Decrypt
3.  Caesar Brute Force
4.  Random Key Encrypt
5.  Random Key Decrypt
6.  File Encrypt
7.  File Decrypt
8.  Generate Key File
9.  Generate Custom Wordlist
10. Exit
Enter the number of your desired option and follow the prompts.

📌 Menu Options
Option	Description
1. Encrypt	Enter text and a shift key (1–25) to encrypt
2. Decrypt	Enter encrypted text and the original shift key to decrypt
3. Caesar Brute Force	Try all 25 possible keys on a ciphertext
4. Random Key Encrypt	Encrypts text using a randomly generated key
5. Random Key Decrypt	Decrypts text using a previously saved random key
6. File Encrypt	Reads a .txt file and writes an encrypted version
7. File Decrypt	Reads an encrypted file and writes the decrypted version
8. Generate Key File	Generates a random key and saves it to a file
9. Generate Custom Wordlist	Creates a password wordlist based on personal info
10. Exit	Exits the program


💡 Example
Encrypting text with shift key 3:
Enter text to encrypt: Hello World
Enter shift key (1-25): 3

Original Text : Hello World
Shift Key     : 3
Encrypted Text: Khoor Zruog
Decrypting with the same key:
Enter encrypted text: Khoor Zruog
Enter shift key (1-25): 3

Decrypted Text: Hello World

📁 Project Structure
caesar-cipher-tool/
│
└── main.cpp        # All source code (main + 8 functions)

⚠️ Notes
    • Only alphabetic characters are shifted; numbers, spaces, and symbols are preserved as-is.
    • The wordlist generator is intended for ethical use only (e.g., recovering your own forgotten passwords).
    • Key files are saved as plain text — keep them secure.
    • The brute force feature tries all 25 keys and prints all results; identify the correct one by readability.
