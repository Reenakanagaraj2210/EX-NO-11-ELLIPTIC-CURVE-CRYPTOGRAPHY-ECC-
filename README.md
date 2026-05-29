# EX-NO-11-ELLIPTIC-CURVE-CRYPTOGRAPHY-ECC

## Aim:
To Implement ELLIPTIC CURVE CRYPTOGRAPHY(ECC)


## ALGORITHM:

1. Elliptic Curve Cryptography (ECC) is a public-key cryptography technique based on the algebraic structure of elliptic curves over finite fields.

2. Initialization:
   - Select an elliptic curve equation \( y^2 = x^3 + ax + b \) with parameters \( a \) and \( b \), along with a large prime \( p \) (defining the finite field).
   - Choose a base point \( G \) on the curve, which will be used for generating public keys.

3. Key Generation:
   - Each party selects a private key \( d \) (a random integer).
   - Calculate the public key as \( Q = d \times G \) (using elliptic curve point multiplication).

4. Encryption and Decryption:
   - Encryption: The sender uses the recipient’s public key and the base point \( G \) to encode the message.
   - Decryption: The recipient uses their private key to decode the message and retrieve the original plaintext.

5. Security: ECC’s security relies on the Elliptic Curve Discrete Logarithm Problem (ECDLP), making it highly secure with shorter key lengths compared to traditional methods like RSA.

## Program:

```
#include <stdio.h>

// Function to perform modulo operation
int mod(int a, int p)
{
    int result = a % p;
    if(result < 0)
        result += p;
    return result;
}

int main()
{
    int p, a, b;
    int Gx, Gy;
    int privateKey;
    int publicKeyX, publicKeyY;

    // Input curve parameters
    printf("Enter prime number p: ");
    scanf("%d", &p);

    printf("Enter curve parameter a: ");
    scanf("%d", &a);

    printf("Enter curve parameter b: ");
    scanf("%d", &b);

    // Base point G
    printf("Enter base point G(x y): ");
    scanf("%d %d", &Gx, &Gy);

    // Private key
    printf("Enter private key: ");
    scanf("%d", &privateKey);

    // Simplified public key calculation
    publicKeyX = mod(privateKey * Gx, p);
    publicKeyY = mod(privateKey * Gy, p);

    printf("\nElliptic Curve Equation:\n");
    printf("y^2 = x^3 + %dx + %d (mod %d)\n", a, b, p);

    printf("\nBase Point G = (%d, %d)\n", Gx, Gy);

    printf("\nPrivate Key = %d\n", privateKey);

    printf("Public Key Q = (%d, %d)\n", publicKeyX, publicKeyY);

    return 0;
}


```

## Output:

<img width="940" height="584" alt="image" src="https://github.com/user-attachments/assets/4f3c1f90-6b8b-4344-9446-7da23cd6970f" />

## Result:
The ELLIPTIC-CURVE-CRYPTOGRAPHY-ECC program is executed successfully

