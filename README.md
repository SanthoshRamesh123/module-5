# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM:
To write a C Program to find area of rectangle using pointer.

## ALGORITHM:
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>

int main() {
    float length, breadth, area;
    float *ptrLength, *ptrBreadth;

    // Assigning addresses to pointers
    ptrLength = &length;
    ptrBreadth = &breadth;

    // Taking input
    printf("Enter length of rectangle: ");
    scanf("%f", ptrLength);

    printf("Enter breadth of rectangle: ");
    scanf("%f", ptrBreadth);

    // Calculating area using dereferenced pointers
    area = (*ptrLength) * (*ptrBreadth);

    // Displaying the result
    printf("Area of rectangle = %.2f\n", area);

    return 0;
}
~~~

## OUTPUT:
![image](https://github.com/user-attachments/assets/548f65f9-af86-44ab-b784-57002d773cc2)

		       	
## RESULT:
Thus the program to find area of rectangle using pointer has been executed successfully
 
# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM:
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM:
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    // Allocate memory for 8 characters (7 letters + 1 for null terminator)
    char *message = (char *)malloc(8 * sizeof(char));

    // Check if memory allocation was successful
    if (message == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    // Copy the string into the allocated memory
    strcpy(message, "WELCOME");

    // Print the message
    printf("%s\n", message);

    // Free the allocated memory
    free(message);

    return 0;
}
~~~

## OUTPUT:
![image](https://github.com/user-attachments/assets/698fea01-f981-46fe-9569-d02efff70ec6)

## RESULT:
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 

# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM:

To write a C Program to store the student information and display it using structure.

## ALGORITHM:

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>

// Define a structure for student
struct Student {
    int rollNumber;
    char name[50];
    float marks;
};

int main() {
    struct Student s;  // Declare a structure variable

    // Input student details
    printf("Enter student roll number: ");
    scanf("%d", &s.rollNumber);

    printf("Enter student name: ");
    scanf(" %[^\n]", s.name); // Read full name including spaces

    printf("Enter student marks: ");
    scanf("%f", &s.marks);

    // Display student details
    printf("\n--- Student Information ---\n");
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
~~~


## OUTPUT:
![image](https://github.com/user-attachments/assets/fb1a1cb5-588f-45c6-837d-2a631026e443)

## RESULT:

Thus the program to store the student information and display it using structure has been executed successfully.
 
# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM:
~~~
#include <stdio.h>

// Define a structure for Employee
struct Employee {
    int id;
    char name[50];
    float basicSalary;
    float grossSalary;
};

int main() {
    struct Employee emp[3];
    int i;

    // Read employee details
    for (i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d:\n", i + 1);

        printf("ID: ");
        scanf("%d", &emp[i].id);

        printf("Name: ");
        scanf(" %[^\n]", emp[i].name);

        printf("Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);

        // Calculate gross salary
        float hra = 0.20f * emp[i].basicSalary;
        float da = 0.80f * emp[i].basicSalary;
        emp[i].grossSalary = emp[i].basicSalary + hra + da;
    }

    // Display employee details with Gross Salary
    printf("\n--- Employee Details ---\n");
    for (i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("ID: %d\n", emp[i].id);
        printf("Name: %s\n", emp[i].name);
        printf("Basic Salary: %.2f\n", emp[i].basicSalary);
        printf("Gross Salary: %.2f\n", emp[i].grossSalary);
    }

    return 0;
}
~~~


 ## OUTPUT:
 ![image](https://github.com/user-attachments/assets/7100a773-993e-4f96-924d-9323fea0b28c)
 
 ## RESULT:

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 

# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM

Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM:
~~~
#include <stdio.h>

// Define structure for Student
struct Student {
    int rollNumber;
    char name[50];
    float marks1, marks2, marks3;
    float total;
    float average;
};

int main() {
    struct Student s;

    // Input student details
    printf("Enter Roll Number: ");
    scanf("%d", &s.rollNumber);

    printf("Enter Name: ");
    scanf(" %[^\n]", s.name);

    printf("Enter marks for Subject 1: ");
    scanf("%f", &s.marks1);

    printf("Enter marks for Subject 2: ");
    scanf("%f", &s.marks2);

    printf("Enter marks for Subject 3: ");
    scanf("%f", &s.marks3);

    // Calculate total and average
    s.total = s.marks1 + s.marks2 + s.marks3;
    s.average = s.total / 3.0;

    // Display the results
    printf("\n--- Student Result ---\n");
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Name: %s\n", s.name);
    printf("Total Marks: %.2f\n", s.total);
    printf("Average Marks: %.2f\n", s.average);

    return 0;
}

~~~

## OUTPUT:
![image](https://github.com/user-attachments/assets/ec3db6ab-5655-4246-9c82-eff8f28636a3)

## RESULT:

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


