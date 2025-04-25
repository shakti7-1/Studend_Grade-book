#  Student class to store student name and grades
class Student:
    def __init__(self, name, grades):
        # This method initializes the student with a name and a list of grades
        self.name = name
        self.grades = grades

    def average(self):
        # Calculates and returns the average of the student's grades
        return sum(self.grades) / len(self.grades)

# A list to store all student objects
students = []

# Function to add a new student with their grades
def add_student():
    name = input("Student name: ")  # Take the student's name as input
    grades = list(map(int, input("Enter grades separated by space: ").split()))
    # Take multiple grades as input, split them, and convert to integers
    students.append(Student(name, grades))  # Create a Student object and add to list

# Function to display each student's average grade
def view_averages():
    for student in students:
        print(f"{student.name}: Avg = {student.average():.2f}")
        # Display name and average rounded to 2 decimal places

# Main program loop
def main():
    while True:
        # Menu for user to choose an action
        print("\n1. Add Student\n2. View Averages\n3. Exit")
        ch = input("Choice: ")
        if ch == "1":
            add_student()  # Call function to add student
        elif ch == "2":
            view_averages()  # Call function to view averages
        elif ch == "3":
            break  # Exit the loop and end the program
        else:
            print("Invalid choice!")  # Error message for wrong input

# Entry point of the program
if __name__ == "__main__":
    main()  # Start the program
