Trackademy  
Q1 Project -Task Management System (Python) 

 📖 Overview  
Trackademy is a basic task management system scripted in Python that has been created to help you stay organized in generating and managing tasks.  
It enables the creation, viewing, editing, and deletion of tasks, as well as tracking deadlines and automatically marking tasks as overdue.    

Objectives  
- To create a practical and simple tool for students to use for managing their academic tasks    
- To allow grade calculation based on given scores and weight percentages.  
- To provide a centralized system for tracking assignments, deadlines, and class schedules.  
- To encourage productivity by helping students stay organized.  

Features planned  
- Include tasks with a title, an optional description, and a deadline.  
- See the list of all tasks, including the status notes (In Progress, Completed, Overdue).  
- Edit information about tasks.  
- Remove tasks that are no longer required.  
- Automatic pick out and marking of late jobs.  

 Inputs &  Outputs  
Inputs:
Task title (string)  
- Optional description of task (string)  
Time and date deadline  
- The status of tasks (In progress / completed)  

Outputs:
The list of tasks is accompanied by information and status.  
Messages of pending assignments.  
Added, edited, or deleted task confirmation messages.  

Flow of Program (Pseudocode)  

print("Welcome to Trackademia")

grades = {}                # Saves grades with the name of the subject 
assignments = []            # Saves assignments including the deadlines 
schedules = {}               # Saves schedules with subject name 

while True:                                   #A repeat loop :>
    print("Menu:") 
    print("1 - Add Grade")
    print("2 - View Grades")
    print("3 - Add Assignment")
    print("4 - View Assignments")
    print("5 - Add Class Schedule")
    print("6 - View Schedules")
    print("0 - Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        subject = input("Enter the name of the subject:")
        grade = float(input("Enter grades:"))
        grades[subject] = grade
        print("Grades saved")

    elif choice == "2":
        if grades:
            print("Grades:")
            for subject, grade in grades.items():
                print(f"{subject}:{grade}")
            average = sum(grades.values())/len(grades)
            print(f"Average Grade: {average:.2f}")
        else:
            print("No grades saved yet:>")

    elif choice == "3":
        name = input("Enter assignment's name: ")
        deadline = input("Enter the deadline: ")
        assignments.append((name, deadline))
        print("Assignment saved!")

    elif choice == "4":
        if assignments:
            print("Assignments:")
            for name, deadline in assignments:
                print(f"{name} - Due: {deadline}")
        else:
            print("No assignments saved yet")

    elif choice == "5":
        subject = input("Enter subject name: ")
        schedule = input("Enter schedule (Day & Time): ")
        schedules[subject] = schedule
        print("Schedule saved!")

    elif choice == "6":
        if schedules:
            print("Schedules:")
            for subject, time in schedules.items():
                print(f"{subject} - {time}")
        else:
            print("No schedules saved yet.")

    elif choice == "0":
        print("Thank you for using Trackademia!")
        break

    else:
        print("Invalid choice. Please try again.") #when the user types something thats not in the choices
