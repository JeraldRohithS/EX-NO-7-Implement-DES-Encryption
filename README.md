# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
from Crypto.Cipher import DES
from Crypto.Util.Padding import pad, unpad

# DES key must be 8 bytes long
key = b'12345678'

# Create DES cipher
cipher = DES.new(key, DES.MODE_ECB)

# Plaintext
plaintext = input("Enter the plaintext: ")

# Encrypt
padded_text = pad(plaintext.encode(), DES.block_size)
ciphertext = cipher.encrypt(padded_text)

print("Encrypted Text (Hex):", ciphertext.hex())

# Decrypt
decipher = DES.new(key, DES.MODE_ECB)
decrypted_text = unpad(decipher.decrypt(ciphertext), DES.block_size)

print("Decrypted Text:", decrypted_text.decode())

```



## Output:

<img width="523" height="151" alt="image" src="https://github.com/user-attachments/assets/aa84deb2-40ed-459e-bab6-3e0ba659f84a" />


## Result:
  The program is executed successfully

