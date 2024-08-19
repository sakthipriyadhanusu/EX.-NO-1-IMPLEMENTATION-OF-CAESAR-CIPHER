![image](https://github.com/user-attachments/assets/27119cc7-023c-419e-ab7e-8664216046cf)# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

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

void caesarCipher(char* text, int shift) {
    for (int i = 0; text[i] != '\0'; i++) {
        char ch = text[i];
        
 
        if (isupper(ch)) {
            ch = (ch + shift - 'A') % 26 + 'A';
        }
        
        else if (islower(ch)) {
            ch = (ch + shift - 'a') % 26 + 'a';
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

  
    caesarCipher(text, shift);

  
    printf("Ciphertext: %s\n", text);
    return 0;
}
```

## OUTPUT:
![Screenshot 2024-08-19 144316](https://github.com/user-attachments/assets/34e0dfe1-8716-41c0-afd7-d05d2fcece57)


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
