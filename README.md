# To-do-list-using-Python
import datetime

tasks = []

def add_task():
    task = input("Enter task: ")
    tasks.append(task)
    print("Task added!")

def view_tasks():
    if not tasks:
        print("No tasks in the list.")
    else:
        print("Your tasks:")
        for i, task in enumerate(tasks):
            print(f"{i+1}. {task}")

def complete_task():
    if not tasks:
        print("No tasks to complete.")
    else:
        view_tasks()
        index = int(input("Enter index of task to complete: ")) - 1
        if 0 <= index < len(tasks):
            del tasks[index]
            print("Task completed!")
        else:
            print("Invalid index.")

while True:
    print("\nTo-Do List:")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Complete Task")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == '1':
        add_task()
    elif choice == '2':
        view_tasks()
    elif choice == '3':
        complete_task()
    elif choice == '4':
        break
    else:
        print("Invalid choice.")
