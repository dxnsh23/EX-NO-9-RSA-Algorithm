# EX-NO-9-RSA-Algorithm
# Name : S DINESH RAGHAVENDARA
# REG NO: 212224040078

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:
```
#include <stdio.h>

int gcd(int a,int b){
    while(b!=0){ a=a%b; int t=a; a=b; b=t; }
    return a;
}

int main(){
    int p,q,n,phi,e=2,d=1,msg,enc,dec,i;
    char name[50];
    printf("Enter your name: ");
    scanf(" %[^\n]",name);

    printf("Enter prime p: ");
    scanf("%d",&p);
    printf("Enter prime q: ");
    scanf("%d",&q);

    n=p*q;
    phi=(p-1)*(q-1);

    while(gcd(e,phi)!=1) e++;

    for(i=1;i<phi;i++)
        if((e*i)%phi==1){ d=i; break; }

    printf("Public key: (%d,%d)\n",n,e);
    printf("Private key: (%d,%d)\n",n,d);

    printf("Enter message: ");
    scanf("%d",&msg);

    enc=1; for(i=0;i<e;i++) enc=(enc*msg)%n;
    dec=1; for(i=0;i<d;i++) dec=(dec*enc)%n;

    printf("Encrypted: %d\n",enc);
    printf("Decrypted: %d\n",dec);

    return 0;
}
```


## Output:

<img width="1919" height="896" alt="image" src="https://github.com/user-attachments/assets/331b6095-7bfe-419d-b0f4-4b8c9a5af2c8" />



## Result:
 The program is executed successfully.
