# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <ctype.h>

void caesarCipher(char* text, int shift, int decrypt) {
    // If decrypting, reverse the shift
    if (decrypt) {
        shift = -shift;
    }

    for (int i = 0; text[i] != '\0'; i++) {
        char ch = text[i];
        
        if (isupper(ch)) {
            ch = (ch - 'A' + shift + 26) % 26 + 'A'; // Adjust for uppercase
        }
        else if (islower(ch)) {
            ch = (ch - 'a' + shift + 26) % 26 + 'a'; // Adjust for lowercase
        }

        text[i] = ch;
    }
}

int main() {
    char text[100];
    int shift;

    printf("Enter a plaintext: ");
    fgets(text, sizeof(text), stdin);

    printf("Enter shift value: ");
    scanf("%d", &shift);

    // Perform encryption
    caesarCipher(text, shift, 0);
    printf("Ciphertext: %s\n", text);

    // Perform decryption
    caesarCipher(text, shift, 1);
    printf("Decrypted text: %s\n", text);

    return 0;
}
```
## OUTPUT:
![Screenshot 2024-10-28 134544](https://github.com/user-attachments/assets/8ec3bb62-6acd-49c9-abde-609794c93607)


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
