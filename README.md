# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```C
#include <stdio.h>
#include <string.h>

int main() {
    char text[100];
    int key;

    printf("Enter text: ");
    scanf(" %[^\n]", text);

    printf("Enter key: ");
    scanf("%d", &key);

    int len = strlen(text);
    char rail[key][len];

    // Fill with space
    for (int i = 0; i < key; i++)
        for (int j = 0; j < len; j++)
            rail[i][j] = ' ';

    int row = 0, dir = 1;

    // Zig-zag fill
    for (int i = 0; i < len; i++) {
        rail[row][i] = text[i];

        if (row == 0)
            dir = 1;
        else if (row == key - 1)
            dir = -1;

        row += dir;
    }

    // Print encrypted text
    printf("Encrypted text: ");
    for (int i = 0; i < key; i++)
        for (int j = 0; j < len; j++)
            if (rail[i][j] != ' ')
                printf("%c", rail[i][j]);

    return 0;
}
```


# OUTPUT

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/f6e4dd9e-2993-4cdc-93cb-d2dbcfd4d480" />


# RESULT

The program implementing the Rail Fence cipher for encryption and decryption has been successfully executed, and the results have been verified.

