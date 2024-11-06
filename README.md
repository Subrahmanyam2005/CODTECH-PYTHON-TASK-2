 This Python program provides a basic yet efficient way to track and manage student grades. Below is an expanded description of each part of the code, breaking down its functions, logic, and potential enhancements.

1. Functions for Grade Calculation

The program contains three core functions that deal with grade processing:

calculate_average(grades): This function calculates the average of grades stored in a list. If the list is empty (to handle the case when no grades are entered), it returns 0.

def calculate_average(grades):
    if not grades:
        return 0
    return sum(grades) / len(grades)

letter_grade(average): Converts a numerical average to a letter grade. The grade boundaries are defined as follows:

90 and above: A

80 to 89: B

70 to 79: C

60 to 69: D

Below 60: F


def letter_grade(average):
    if average >= 90:
        return 'A'
    elif average >= 80:
        return 'B'
    elif average >= 70:
        return 'C'
    elif average >= 60:
        return 'D'
    else:
        return 'F'

gpa(average): Converts the average grade into a GPA on a 4.0 scale:

90 and above: 4.0

80 to 89: 3.0

70 to 79: 2.0

60 to 69: 1.0

Below 60: 0.0


def gpa(average):
    if average >= 90:
        return 4.0
    elif average >= 80:
        return 3.0
    elif average >= 70:
        return 2.0
    elif average >= 60:
        return 1.0
    else:
        return 0.0


2. Main Program Flow (main function)

The main function is designed as a simple menu-driven interface that allows the user to perform several actions interactively.

def main():
    grades = {}

This dictionary (grades) holds the subject as the key and its corresponding grade as the value. For example, if a student has a grade of 85 in Math, grades would store it as {'Math': 85}.

Menu Options

1. Input Grade:

The user is prompted to enter a subject and its grade.

The program adds this entry to the grades dictionary if the grade is valid (numerical).

This input feature allows students to add multiple subjects and grades.


subject = input("Enter the subject name: ")
grade = float(input(f"Enter the grade for {subject}: "))
grades[subject] = grade


2. Display Grades:

If there are grades recorded, the program displays each subject and its corresponding grade.

If no grades have been entered yet, a message notifies the user.


for subject, grade in grades.items():
    print(f"{subject}: {grade}")


3. Calculate Average Grade:

If there are any grades in the dictionary, the program calculates the average, determines the letter grade, and calculates the GPA.

If no grades are available, it displays a message indicating that calculation is not possible.


average = calculate_average(list(grades.values()))
letter = letter_grade(average)
gpa_value = gpa(average)
print(f"\nAverage Grade: {average:.2f}")
print(f"Letter Grade: {letter}")
print(f"GPA: {gpa_value:.2f}")


4. Exit:

Exits the program loop and ends the program.




3. Error Handling

The program includes basic error handling to ensure that only numerical inputs are accepted for grades. If an invalid input (non-numeric) is entered, it displays an error message without crashing.

try:
    grade = float(input(f"Enter the grade for {subject}: "))
except ValueError:
    print("Invalid input. Please enter a valid number for the grade.")

4. Running the Program

The program uses an infinite loop to keep displaying the menu until the user chooses to exit (option 4).

It’s launched by calling main() at the end of the script, making it immediately interactive upon execution.


Potential Enhancements

This basic program could be expanded in several ways:

Save and Load Functionality: Add functions to save grades to a file and load them later, enabling data persistence between program runs.

Weighted Grades: Allow users to input weighted grades for subjects that count differently (e.g., final exams).

Credits and GPA: Enable calculations that factor in course credits, providing a more accurate GPA.

User Authentication: Include an option for multiple users, each with a unique set of grades.


This program serves as a great foundation for student grade management, and with added functionality, it can be tailored to a range of educational needs.


output:
![Screenshot (101)](https://github.com/user-attachments/assets/169146ef-5341-4eff-b87d-f1857e63d98b)
