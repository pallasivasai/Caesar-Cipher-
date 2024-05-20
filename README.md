# Caesar Cipher Encryption/Decryption Tool

This is a simple Python program that allows users to encrypt and decrypt messages using the Caesar cipher algorithm. The program provides a command-line interface to input messages and shift values for the encryption and decryption process.

## Features

- Encrypt messages using a specified shift value.
- Decrypt messages using the same shift value used for encryption.
- Supports both uppercase and lowercase letters.
- Retains non-alphabetic characters (such as punctuation and spaces) in the original message.

## How It Works

The Caesar cipher is a type of substitution cipher in which each letter in the plaintext is shifted a certain number of places down the alphabet. For example, with a shift of 1, 'A' would be replaced by 'B', 'B' would become 'C', and so on. The same shift is used for both encryption and decryption, but in the opposite direction for decryption.

## Code Explanation

### Functions

- `encrypt(message, shift)`: Encrypts the given message by shifting each letter by the specified shift value.
- `decrypt(message, shift)`: Decrypts the given message by shifting each letter back by the specified shift value. It uses the `encrypt` function with a negative shift.
- `main()`: The main function that provides a command-line interface for the user to choose between encryption, decryption, and exiting the program.

### Encryption Logic

```python
def encrypt(message, shift):
    encrypted_message = ""
    for char in message:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            encrypted_message += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        else:
            encrypted_message += char
    return encrypted_message
```
### Decryption Logic
```
def decrypt(message, shift):
    return encrypt(message, -shift)
```
### Usage
1.Run the script:

```
python caesar_cipher.py
```
2.Follow the on-screen prompts to choose an option:

    - Encrypt: Enter 1 to encrypt a message.
    - Decrypt: Enter 2 to decrypt a message.
    - Exit: Enter 3 to exit the program.
### Requirements
    - `Python 3.x
