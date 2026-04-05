# Student Data Organizer

This project is a simple Python-based console application that allows
users to manage student information without using functions.\
The system supports adding, displaying, updating, and deleting student
records, as well as listing all unique subjects offered.

------------------------------------------------------------------------

 📌 Features

### 1. Add Student

Allows entering: - Student ID\
- Name\
- Age\
- Date of Birth\
- Grade\
- Subjects (comma-separated)

### 2. Display All Students

Shows all stored student records in a structured format.

### 3. Update Student Information

Modify existing student details using their Student ID.

### 4. Delete Student

Removes a student from the list by Student ID.

### 5. Display Subjects Offered

Lists all unique subjects added across all students.

### 6. Exit

Terminates the program.

------------------------------------------------------------------------

## 🧾 Source Code

``` python
print("Welcome to the Student Data Organizer!")

students = []

while True:
    print("Select an option:")
    print("\n1. Add Student")
    print("2. Display All Students")
    print("3. Update Student Information")
    print("4. Delete Student")
    print("5. Display Subjects Offered")
    print("6. Exit")

    choice = input("Enter your choice: ")
    if choice == "1":
        print("Enter student details:")

        s = {
            "student id": input("Student ID: "),
            "Name": input("Name: "),
            "Age": input("Age: "),
            "Date of birth": input("Date of birth: "),
            "grade": input("Enter grade: "),
            "Subjects": input("Type subjects separated by comma: ").split(",")
        }
        students.append(s)
        print("Student added successfully!")

    elif choice == "2":
        if not students:
            print("No student record found.")
        else:
            for s in students:
                print(f"\nStudent ID: {s['student id']} | Name: {s['Name']} | Age: {s['Age']} | "
                      f"Grade: {s['grade']} | Date of Birth: {s['Date of birth']} | "
                      f"Subjects: {', '.join([sub.strip() for sub in s['Subjects']])}")

    elif choice == "3":
        studentid = input("Enter student ID to update: ")
        for s in students:
            if s["student id"] == studentid:
                s["Name"] = input("Enter new name: ")
                s["Age"] = input("Enter new age: ")
                s["grade"] = input("Enter new Grade: ")
                s["Date of birth"] = input("Enter new Date of birth: ")
                s["Subjects"] = input("Enter new subjects seperated by comma: ").split(',')
                print("Student information updated.")
                break

    elif choice == "4":
        studentid = input("Enter student ID to delete: ")
        for s in students:
            if s["student id"] == studentid:
                students.remove(s)
                print("Student deleted successfully.")
                break

    elif choice == "5":
        subjects = set()
        for s in students:
            for sub in s["Subjects"]:
                subjects.add(sub.strip())

        if subjects:
            print("Subjects Offered:")
            for sub in subjects:
                print("-", sub)
        else:
            print("No subjects available.")
    elif choice == "6":
        print("Exiting program...")
        break

    else:
        print("Invalid choice! Please choose between 1 to 6.")
        print("Student not found.")
```

------------------------------------------------------------------------

## 📂 How to Run

1.  Save the script as `student_data_organizer.py`\

2.  Open a terminal and run:

    ``` bash
    python student_data_organizer.py
    ```

------------------------------------------------------------------------

## ✔️ Author

Converted to README.md by ChatGPT.
