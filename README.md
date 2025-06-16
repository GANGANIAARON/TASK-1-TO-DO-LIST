# TASK-1-TO-DO-LIST
# A To-Do List application is a useful project that helps users manage and organize their tasks efficiently. This project aims to create a command-line or GUI-based application using Python, allowing users to create, update, and track their to-do lists
# Simple Command-Line To-Do List App in Python

todo_list = []

def show_menu():
    print("\n--- TO-DO LIST MENU ---")
    print("1. Show To-Do List")
    print("2. Add Task")
    print("3. Update Task")
    print("4. Delete Task")
    print("5. Exit")

def show_tasks():
    if not todo_list:
        print("No tasks in your to-do list.")
    else:
        for i, task in enumerate(todo_list, start=1):
            print(f"{i}. {task}")

def add_task():
    task = input("Enter the task: ")
    todo_list.append(task)
    print("Task added!")

def update_task():
    show_tasks()
    try:
        task_no = int(input("Enter task number to update: "))
        if 1 <= task_no <= len(todo_list):
            new_task = input("Enter new task: ")
            todo_list[task_no - 1] = new_task
            print("Task updated!")
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")

def delete_task():
    show_tasks()
    try:
        task_no = int(input("Enter task number to delete: "))
        if 1 <= task_no <= len(todo_list):
            todo_list.pop(task_no - 1)
            print("Task deleted!")
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")

while True:
    show_menu()
    choice = input("Enter your choice: ")
    
    if choice == '1':
        show_tasks()
    elif choice == '2':
        add_task()
    elif choice == '3':
        update_task()
    elif choice == '4':
        delete_task()
    elif choice == '5':
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please choose from 1 to 5.")
