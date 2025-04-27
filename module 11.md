

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>
int max_of_four(int n1, int n2, int n3, int n4) {
    int greater = n1;
    if (n2 > greater) {
        greater = n2;
    }
    if (n3 > greater) {
        greater = n3;
    }
    if (n4 > greater) {
        greater = n4;
    }
    return greater;
}
int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("The greatest number is: %d\n", greater);
    return 0;
}
```
Output:



![Screenshot 2025-04-27 202212](https://github.com/user-attachments/assets/98505923-de8b-49c4-8904-7453a1a78077)


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            if ((i & j) > a && (i & j) < k) {
                a = i & j;
            }
            if ((i | j) > o && (i | j) < k) {
                o = i | j;
            }
            if ((i ^ j) > x && (i ^ j) < k) {
                x = i ^ j;
            }
        }
    }
    printf("Maximum AND value: %d\n", a);
    printf("Maximum OR value: %d\n", o);
    printf("Maximum XOR value: %d\n", x);
}
int main() {
    int n, k;
    printf("Enter the values for n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}
```
Output:



![Screenshot 2025-04-27 202350](https://github.com/user-attachments/assets/28ad1321-04d9-4b90-9716-13acabb771b4)


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
void process_requests(int shelves, int queries) {
    int shelarr[shelves][100];
    int nobookarr[shelves];
    int i, j, k, c;
    for (i = 0; i < shelves; i++) {
        nobookarr[i] = 0;
    }
    for (i = 0; i < queries; i++) {
        int query_type, shelf, book;
        printf("\nEnter query type (1 to add a book, 2 to find a book): ");
        scanf("%d", &query_type);
        if (query_type == 1) {
            printf("Enter shelf number (1 to %d): ", shelves);
            scanf("%d", &shelf);
            if (shelf < 1 || shelf > shelves) {
                printf("Invalid shelf number!\n");
                continue;
            }
            printf("Enter book number to add to shelf %d: ", shelf);
            scanf("%d", &book);
            shelarr[shelf - 1][nobookarr[shelf - 1]] = book;
            nobookarr[shelf - 1]++;
            printf("Book %d added to shelf %d.\n", book, shelf);
        } else if (query_type == 2) {
            printf("Enter shelf number to search (1 to %d): ", shelves);
            scanf("%d", &shelf);
            if (shelf < 1 || shelf > shelves) {
                printf("Invalid shelf number!\n");
                continue;
            }
            printf("Enter book number to search: ");
            scanf("%d", &book);
            int found = 0;
            for (j = 0; j < nobookarr[shelf - 1]; j++) {
                if (shelarr[shelf - 1][j] == book) {
                    found = 1;
                    break;
                }
            }
            if (found) {
                printf("Book %d found on shelf %d.\n", book, shelf);
            } else {
                printf("Book %d not found on shelf %d.\n", book, shelf);
            }
        } else {
            printf("Invalid query type!\n");
        }
    }
}
int main() {
    int noshel, noque;
    printf("Enter the number of shelves: ");
    scanf("%d", &noshel);
    printf("Enter the number of queries: ");
    scanf("%d", &noque);
    process_requests(noshel, noque);
    return 0;
}

```

Output:



![Screenshot 2025-04-27 202836](https://github.com/user-attachments/assets/f82f5576-2957-4317-bd3e-c41c869a9a5c)


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter the number of integers: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("The sum of the integers is: %d\n", sum);
    return 0;
}


```

Output:




![Screenshot 2025-04-27 203029](https://github.com/user-attachments/assets/68f3046e-1131-45d6-9f85-6b286107183d)

 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int count = 0;
    int i = 0;
    int inWord = 0;
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);
    while (sentence[i] != '\0') {
        if (isspace(sentence[i])) {
            inWord = 0;
        } else if (!inWord) {
            count++;
            inWord = 1;
        }
        i++;
    }
    printf("Total number of words: %d\n", count);
    return 0;
}

```

Output:




![Screenshot 2025-04-27 203252](https://github.com/user-attachments/assets/1d92d29f-628f-42f4-ada1-ee2881777730)



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
