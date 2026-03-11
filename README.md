# EX-NO-7-Implement-DES-Encryption
# reg no: 212224040078
# Name: S DINESH RAGHAVENDARA
## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
#include <stdio.h> 
#include <string.h> 
 
void xorCrypt(char *in, char *key, char *out, int len) { 
    for (int i = 0; i < len; i++) { 
        out[i] = in[i] ^ key[i % strlen(key)]; 
    } 
    out[len] = '\0'; 
} 
int main() { 
    char msg[100], key[100], enc[100], dec[100]; 
 
    printf ("Enter message: "); 
    fgets(msg, 100, stdin); 
    msg[strcspn(msg, "\n")] = 0; 
 
    printf ("Enter key: "); 
    fgets(key, 100, stdin); 
    key[strcspn(key, "\n")] = 0; 
 
    int len = strlen(msg); 
 
    xorCrypt(msg, key, enc, len); 
    printf ("Encrypted: "); 
    for (int i = 0; i < len; i++) { 
        printf ("%02X ", (unsigned char)enc[i]); 
    } 
    printf ("\n"); 
 
    xorCrypt(enc, key, dec, len); 
    printf ("Decrypted: %s\n", dec); 
 
    return 0; 
}
```



## Output:

<img width="1621" height="900" alt="image" src="https://github.com/user-attachments/assets/c6ae7e84-e411-4535-ad2d-045d7cf95749" />


## Result:
  The program is executed successfully

