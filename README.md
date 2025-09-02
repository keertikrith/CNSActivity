# 🔐 Playfair Cipher in Java

This repository contains a **Java implementation** of the **Playfair Cipher**, a classical polygraphic substitution cipher invented in 1854 by Charles Wheatstone.  
The program supports **encryption and decryption** with detailed debug/print statements for learning and demonstration purposes.

---

## 📖 What is Playfair Cipher?

The Playfair Cipher encrypts pairs of letters (digraphs) instead of single letters, making it more secure than simple substitution ciphers.  
It uses a **5×5 key matrix** constructed from a keyword.  
- The letter **J** is usually combined with **I**.  
- Plaintext is split into digraphs (pairs of letters).  
- Special rules apply when both letters are in the same row, same column, or form a rectangle in the matrix.

---

## ⚙️ How It Works

1. **Key Matrix Generation**
   - Enter a keyword (e.g., `MONARCHY`).  
   - Duplicate letters are removed, and the rest of the alphabet fills the matrix.  

  Example key matrix for `MONARCHY`:

| M | O | N | A | R |
|---|---|---|---|---|
| C | H | Y | B | D |
| E | F | G | I | K |
| L | P | Q | S | T |
| U | V | W | X | Z |


   
2. **Plaintext Preparation**
- Example plaintext: `INSTRUMENTS`  
- Remove spaces and replace `J` with `I`.  
- Split into digraphs: `IN ST RU ME NT SX`  
  (added `X` at the end for padding)

3. **Encryption**
- Digraphs are encrypted according to Playfair rules.  
- Example:  
  ```
  IN → GA
  ST → TL
  RU → MZ
  ME → CL
  NT → RQ
  SX → XA
  ```
- Final ciphertext: **`GATLMZCLRQXA`**

4. **Decryption**
- Ciphertext digraphs are decrypted using the inverse rules.  
- Final decrypted plaintext: **`INSTRUMENTS`**

---

## 🖥️ Running the Program

### Prerequisites
- Java 17+ (tested with Java 21)
- Git installed

### Steps
```bash
# Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Compile
javac PlayfairCipher.java

# Run
java PlayfairCipher
