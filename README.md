# EX-21-POINTERS

# AIM:
Write a C program to convert a 23.65 into 25 using pointer

## ALGORITHM:
1.	Declare a double variable to hold the floating-point number (23.65).
2.	Declare a pointer to double to point to the address of the variable.
3.	Use the pointer to modify the value to 25.0.
4.	Print the modified value.

## PROGRAM:

```c
#include <stdio.h>

int main() {
    double num = 23.65;    // Step 1: Declare and initialize variable
    double *ptr;           // Step 2: Declare pointer

    ptr = &num;            // Point to the address of num

    *ptr = 25.0;           // Step 3: Modify the value through the pointer

    // Step 4: Print the modified value
    printf("Modified value: %.2lf\n", num);

    return 0;
}
```

## OUTPUT:
Modified value: 25.00
 	
## RESULT:
Thus the program to convert a 23.65 into 25 using pointer has been executed successfully.
 
 
# EX-22-FUNCTIONS AND STORAGE CLASS

## AIM:

Write a C program to calculate the Product of first 12 natural numbers using Recursion

## ALGORITHM:

1.	Define a recursive function calculateProduct that takes an integer parameter n.
2.	Return n multiplied by the result of the calculateProduct function called with n - 1.
3.	Declare an integer variable n and an unsigned long long variable product.
4.	Initialize n with the value 12 (for the first 12 natural numbers).
5.	Call the calculateProduct function with n and store the result in the product variable.
6.	Print the result, indicating it is the product of the first 12 natural numbers.

## PROGRAM:

```c
#include <stdio.h>

// Step 1: Define the recursive function
unsigned long long calculateProduct(int n) {
    if (n == 1)
        return 1;  // Base case
    else
        return n * calculateProduct(n - 1);  // Recursive call
}

int main() {
    int n = 12; // Step 4: Initialize n with 12
    unsigned long long product;

    // Step 5: Call the function and store result
    product = calculateProduct(n);

    // Step 6: Print the result
    printf("The product of the first 12 natural numbers is: %llu\n", product);

    return 0;
}
```

## OUTPUT:
The product of the first 12 natural numbers is: 479001600
         		
## RESULT:
Thus the program has been executed successfully.
 
 
# EX-23-ARRAYS AND ITS OPERATIONS

## AIM:

Write C Program to find Sum of each row of a Matrix

## ALGORITHM:

1.	Declare and initialize the matrix with the desired values.
2.	Create a loop to iterate through each row of the matrix.
3.	Inside the loop, calculate the sum of the elements in each row.
4.	Print the sum for each row.

## PROGRAM:

```c
#include <stdio.h>

int main() {
    int rows, cols, i, j;
    
    // Step 1: Declare the matrix
    printf("Enter number of rows and columns: ");
    scanf("%d %d", &rows, &cols);

    int matrix[rows][cols];

    // Input matrix elements
    printf("Enter elements of the matrix:\n");
    for (i = 0; i < rows; i++) {
        for (j = 0; j < cols; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }

    // Step 2, 3, 4: Find and print sum of each row
    for (i = 0; i < rows; i++) {
        int sum = 0;
        for (j = 0; j < cols; j++) {
            sum += matrix[i][j];
        }
        printf("Sum of elements in row %d = %d\n", i + 1, sum);
    }

    return 0;
}
```

## OUTPUT
Enter number of rows and columns: 2 3
Enter elements of the matrix:
1 2 3
4 5 6
Sum of elements in row 1 = 6
Sum of elements in row 2 = 15

## RESULT
Thus the program has been executed successfully.
 

# EX-24-STRINGS

## AIM:

Write C program for the below pyramid string pattern. Enter a string: PROGRAM Enter number of rows: 5 P R O G R A M P R O G R A M P R O G R A M

## ALGORITHM:

1.	Input the number of rows for the pyramid (e.g., num_rows).
2.	Initialize variables:i for the row count (starting from 1),j for the character count (starting from 1)
3.	Start a loop for i from 1 to num_rows (for each row of the pyramid).
4.	Calculate the midpoint position as midpoint = (2 * num_rows - 1) / 2.
5.	End the program.

## PROGRAM:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int num_rows, i, j, k, midpoint, len;

    // Step 1: Input the string and number of rows
    printf("Enter a string: ");
    scanf("%s", str);

    printf("Enter number of rows: ");
    scanf("%d", &num_rows);

    len = strlen(str);  // Find the length of the string

    midpoint = (2 * num_rows - 1) / 2;  // Step 4: Calculate midpoint (though not needed much here)

    // Step 3: Loop for each row
    for (i = 1; i <= num_rows; i++) {
        // Print characters up to string length
        for (j = 0; j < len; j++) {
            printf("%c ", str[j]);
        }
        printf("\n");
    }

    return 0;
}
```

## OUTPUT
Enter a string: PROGRAM
Enter number of rows: 5
P R O G R A M 
P R O G R A M 
P R O G R A M 
P R O G R A M 
P R O G R A M 

## RESULT
Thus the C program to String process executed successfully
 

# EX -25 –DISPLAYING ARRAYS USING POINTERS
## AIM

Write a c program to read and display an array of any 6 integer elements using pointer

## ALGORITHM
Step 1: Start the program.
Step 2: Declare the following:
•	Integer variable i for iteration.
•	Integer variable n to store the number of elements.
•	Integer array arr[10] to hold up to 10 elements.
•	Integer pointer parr and initialize it to point to the array arr.
Step 3: Read the value of n (number of elements) from the user.
Step 4: Loop from i = 0 to i < n:
•	Read an integer value and store it in the address parr + i using pointer arithmetic.
Step 5: Loop from i = 0 to i < n:
•	Print the element at *(parr + i) using pointer dereferencing.
Step 6: End the program.

## PROGRAM

```c
#include <stdio.h>

int main() {
    int i, n;
    int arr[10];       // Step 2: Array to hold up to 10 elements
    int *parr = arr;   // Step 2: Pointer to array
    
    // Step 3: Read the number of elements
    printf("Enter the number of elements (up to 6): ");
    scanf("%d", &n);
    
    // Step 4: Read the array elements using pointer arithmetic
    printf("Enter %d elements:\n", n);
    for (i = 0; i < n; i++) {
        printf("Element %d: ", i + 1);
        scanf("%d", parr + i);  // Storing value at the address parr + i
    }

    // Step 5: Display the array elements using pointer dereferencing
    printf("The elements of the array are:\n");
    for (i = 0; i < n; i++) {
        printf("Element %d: %d\n", i + 1, *(parr + i));  // Dereferencing to get the value
    }

    return 0;
}
```

## OUTPUT

Enter the number of elements (up to 6): 6
Enter 6 elements:
Element 1: 10
Element 2: 20
Element 3: 30
Element 4: 40
Element 5: 50
Element 6: 60
The elements of the array are:
Element 1: 10
Element 2: 20
Element 3: 30
Element 4: 40
Element 5: 50
Element 6: 60

## RESULT
Thus the C program to read and display an array of any 6 integer elements using pointer has been executed
