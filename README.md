## Exercise No-1: Caesar Cipher Program

## Aim:
To implement Caesar Cipher encryption and decryption programs in C.

## Algorithm:

## Encryption:

Take a plaintext message and a shift value.
For each character in the plaintext:
If the character is an uppercase letter, shift it by the given key within the range of A-Z.
If the character is a lowercase letter, shift it by the given key within the range of a-z.
Non-alphabet characters remain unchanged.
Display the encrypted message.

## Decryption:

Take the ciphertext and the same shift value used for encryption.
For each character in the ciphertext:
Reverse the shift applied during encryption within the range of A-Z for uppercase letters and a-z for lowercase letters.
Non-alphabet characters remain unchanged.
Display the decrypted message.

## Encryption Code:
```
#include <stdio.h>
#include <string.h>

void encryptCaesarCipher(char* message, int shift) {
    for (int i = 0; i < strlen(message); i++) {
        char c = message[i];
        
        // Check for uppercase letters
        if (c >= 'A' && c <= 'Z') {
            message[i] = ((c - 'A' + shift) % 26) + 'A';
        }
        // Check for lowercase letters
        else if (c >= 'a' && c <= 'z') {
            message[i] = ((c - 'a' + shift) % 26) + 'a';
        }
    }
}

int main() {
    char message[100];
    int shift;

    printf("Enter a message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = 0;  // Remove newline character

    printf("Enter shift value: ");
    scanf("%d", &shift);

    // Encrypt the message
    encryptCaesarCipher(message, shift);
    printf("Encrypted Message: %s\n", message);

    return 0;
}
```

## Decryption Code:
```
#include <stdio.h>
#include <string.h>

void decryptCaesarCipher(char* message, int shift) {
    for (int i = 0; i < strlen(message); i++) {
        char c = message[i];
        
        // Check for uppercase letters
        if (c >= 'A' && c <= 'Z') {
            message[i] = ((c - 'A' - shift + 26) % 26) + 'A';
        }
        // Check for lowercase letters
        else if (c >= 'a' && c <= 'z') {
            message[i] = ((c - 'a' - shift + 26) % 26) + 'a';
        }
    }
}

int main() {
    char message[100];
    int shift;

    printf("Enter an encrypted message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = 0;  // Remove newline character

    printf("Enter shift value used for encryption: ");
    scanf("%d", &shift);

    // Decrypt the message
    decryptCaesarCipher(message, shift);
    printf("Decrypted Message: %s\n", message);

    return 0;
}
```

## Sample Output for Encryption:
![image](https://github.com/user-attachments/assets/02d05600-4123-48e9-961a-b9ee2c0442ab)


## Sample Output for Decryption:
![image](https://github.com/user-attachments/assets/669fccee-17e2-4dbc-b83b-5a69f4fb90cd)


## RESULT:
The Caesar Cipher encryption and decryption programs were successfully implemented in C.
