#include <stdio.h>
#include <string.h>

#define MAX 100

struct Student {
    int roll;
    char name[50];
    float marks;
};

struct Student s[MAX];
int count = 0;

// Add student
void addStudent() {
    printf("\nEnter Roll No: ");
    scanf("%d", &s[count].roll);

    printf("Enter Name: ");
    scanf("%s", s[count].name);

    printf("Enter Marks: ");
    scanf("%f", &s[count].marks);

    count++;
    printf("Student added successfully!\n");
}

// Display all students
void displayStudents() {
    if (count == 0) {
        printf("\nNo records found!\n");
        return;
    }

    printf("\nStudent Records:\n");
    for (int i = 0; i < count; i++) {
        printf("Roll: %d | Name: %s | Marks: %.2f\n",
               s[i].roll, s[i].name, s[i].marks);
    }
}

// Search student
void searchStudent() {
    int roll;
    printf("\nEnter Roll No to search: ");
    scanf("%d", &roll);

    for (int i = 0; i < count; i++) {
        if (s[i].roll == roll) {
            printf("Found: Roll: %d | Name: %s | Marks: %.2f\n",
                   s[i].roll, s[i].name, s[i].marks);
            return;
        }
    }

    printf("Student not found!\n");
}

int main() {
    int choice;

    while (1) {
        printf("\n===== Student Management System =====\n");
        printf("1. Add Student\n");
        printf("2. Display Students\n");
        printf("3. Search Student\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: addStudent(); break;
            case 2: displayStudents(); break;
            case 3: searchStudent(); break;
            case 4: return 0;
            default: printf("Invalid choice!\n");
        }
    }

    return 0;
}# Student-Management-System-
This project is a console-based Student Management System developed in C. It demonstrates basic CRUD operations like adding, displaying, and searching student records using structures, loops, and functions.
