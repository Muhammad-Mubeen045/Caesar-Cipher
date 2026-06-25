# 🔐 Caesar Cipher Tool

A C++ command-line application for text and file encryption/decryption using the Caesar Cipher algorithm — built as a hands-on introduction to the foundations of modern cryptography.

> Caesar Cipher is considered outdated in today's world, but it remains one of the best starting points for beginners. Every expert once started with the basics — always take small steps as a warmup before the big leap.

----

## 📋 Table of Contents

- [Features](#-features)
- [Getting Started](#-getting-started)
- [Menu Overview](#-menu-overview)
- [Encryption](#1-encryption)
- [Decryption](#2-decryption)
- [Brute Force](#3-brute-force)
- [File Encryption](#4-file-encryption)
- [File Decryption](#5-file-decryption)
- [How It Works](#-how-it-works)
- [Notes](#-notes)
- [Contributors](#-contributors)

---

## ✨ Features

- **Encrypt** plain text with a custom shift key (1–25)
- **Decrypt** cipher text using the original shift key
- **Brute Force** — tries all 25 possible keys on any cipher text
- **File Encryption** — encrypts an entire `.txt` file and saves the output
- **File Decryption** — decrypts an encrypted file back to plain text
- Input validation on all menus — handles invalid keys and bad input gracefully

---

## 🚀 Getting Started

### Prerequisites

- A C++ compiler (`g++`, `clang++`, MSVC, etc.)

### Compile

```bash
g++ -o caesar_cipher caeser_code.cpp
```

### Run

```bash
./caesar_cipher         # Linux / Kali / macOS
caesar_cipher.exe       # Windows
```

---

## 🖥️ Menu Overview

```
========================================
        CAESAR CIPHER PROGRAM
========================================
  1. Encrypt
  2. Decrypt
  3. Brute Force
  4. Encrypt File
  5. Decrypt File
  6. Exit
========================================
Enter your choice:
```

---

## 1. Encryption

Encrypts plain text by shifting each alphabetic character forward by the given key. Numbers, spaces, and special characters are preserved as-is.

### Example

```
Enter your choice: 1
Please Enter your text: Hello World!
Please Enter number to shift: 3

Khoor Zruog!
```

**How the shift works:**

| Original | Shift | Encrypted |
|----------|-------|-----------|
| H        | +3    | K         |
| e        | +3    | h         |
| l        | +3    | o         |
| o        | +3    | r         |
| (space)  | —     | (space)   |
| W        | +3    | Z         |

---

## 2. Decryption

Decrypts cipher text by shifting each character backward by the same key used during encryption.

### Example

```
Enter your choice: 2
Please Enter your text: Khoor Zruog!
Please Enter number to shift: 3

Hello World!
```

> ⚠️ You must use the **same key** that was used to encrypt. Without it, decryption produces incorrect output.

---

## 3. Brute Force

No key? No problem. Brute Force tries all 25 possible shift values and prints every result — you identify the correct one by readability.

### Example

```
Enter your choice: 3
Please Enter your text: Khoor Zruog

With Shift 1:
Jgnnq Yqtnf
With Shift 2:
Ifmmp Xpsme
With Shift 3:
Hello World    ✅ <- This is the correct one
With Shift 4:
Gdkkn Vnqkc
...
```

Useful when you have an encrypted message but don't know the key.

---

## 4. File Encryption

Reads a `.txt` file line by line, encrypts each line using the given shift key, and writes the result to a new output file.

### Example

**Input file** (`message.txt`):
```
Meet me at midnight.
Bring the documents.
```

**Terminal:**
```
Enter your choice: 4
Enter shift (1-25): 7
Enter input filename: message.txt
Enter output filename: encrypted.txt

Encrypted file saved to: encrypted.txt
```

**Output file** (`encrypted.txt`):
```
Tlla tl ha tpkupnoa.
Iypun aol kvjbtlua.
```

---

## 5. File Decryption

Reads an encrypted file and reverses the cipher using the same shift key, writing the decrypted content to a new file.

### Example

**Input file** (`encrypted.txt`):
```
Tlla tl ha tpkupnoa.
Iypun aol kvjbtlua.
```

**Terminal:**
```
Enter your choice: 5
Enter shift (1-25): 7
Enter input filename: encrypted.txt
Enter output filename: decrypted.txt

Decrypted file saved to: decrypted.txt
```

**Output file** (`decrypted.txt`):
```
Meet me at midnight.
Bring the documents.
```

---

## 🔬 How It Works

The Caesar Cipher shifts each letter in the alphabet by a fixed number (the key):

**Encryption formula:**
```
Encrypted = (Original - 'A' + shift) % 26 + 'A'
```

**Decryption formula:**
```
Decrypted = (Encrypted - 'A' - shift + 26) % 26 + 'A'
```

The `+ 26` in decryption prevents negative values when the shift wraps around the beginning of the alphabet (e.g., decrypting `A` with shift 3 → `X`).

---

## 📁 Project Structure

```
Caeser-Cipher/
│
├── caeser_code.cpp     # Full source — all functions in one file
└── README.md
```

---

## ⚠️ Notes

- Only **alphabetic characters** are shifted — numbers, spaces, and symbols remain unchanged.
- The valid key range is **1 to 25**. The program re-prompts on invalid input.
- File paths are relative to where you run the program from.
- The Brute Force option prints all 25 results — look for the readable one.
- Key files are not stored by the program — remember your shift key to decrypt later.

----

*Start simple. Think deep. Build secure.* 🔐
