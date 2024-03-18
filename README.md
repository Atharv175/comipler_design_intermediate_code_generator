# comipler_design_intermediate_code_generator

#include <stdio.h>

char precedence1(char str[], int n) {
    char t1 = '\0'; // Initialize t1
    for (int i = 0; i < n; i++) {
        if (str[i] == '*') {
            // Assuming precedence1() is supposed to return a character
            // Update t1 with the substring representing the operation
            t1 = str[i - 1];
            printf("t1=%c%c%c\n", t1, str[i], str[i + 1]); // Print t1
        }
    }
    return t1;
}

char precedence2(char str[], int n, char t1) {
    char t2 = '\0'; // Initialize t2
    for (int i = 0; i < n; i++) {
        if (str[i] == '+') {
            // Update t2 with the substring representing the operation
            t2 = str[i - 1];
            printf("t2=a+t1"); // Print t2
            printf("\n");
        }
    }
    return t2; // Return t2
}

void precedence3(char str[], char t2) { // Changed return type to void
    char x = t2;
    printf("x=t2"); // Print x
}

int main() {
    char str[50];

    printf("Enter a string : ");
    fgets(str, sizeof(str), stdin); // fgets instead of gets to prevent buffer overflow

    int n = 0;
    while (str[n] != '\0' && str[n] != '\n') {
        n++; // Calculate string length
    }

    char t1 = precedence1(str, n);
    char t2 = precedence2(str, n, t1);
    precedence3(str, t2);

    return 0;
}
