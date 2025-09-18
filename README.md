# my-python-projects
my coding practise projects and experiments
# todo_app.py

def show_menu():
    print("\n--- TO-DO LIST APP ---")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Delete Task")
    print("4. Exit")

def add_task(tasks):
    task = input("Enter new task: ")
    tasks.append(task)
    print(f"Task '{task}' added successfully!")

def view_tasks(tasks):
    if not tasks:
        print("No tasks yet!")
    else:
        print("\nYour Tasks:")
        for i, task in enumerate(tasks, start=1):
            print(f"{i}. {task}")

def delete_task(tasks):
    view_tasks(tasks)
    if tasks:
        try:
            task_no = int(input("Enter task number to delete: "))
            removed = tasks.pop(task_no - 1)
            print(f"Task '{removed}' deleted!")
        except (ValueError, IndexError):
            print("Invalid task number!")

def main():
    tasks = []
    while True:
        show_menu()
        choice = input("Choose an option: ")
        
        if choice == "1":
            add_task(tasks)
        elif choice == "2":
            view_tasks(tasks)
        elif choice == "3":
            delete_task(tasks)
        elif choice == "4":
            print("Goodbye!")
            break
        else:
            print("Invalid choice, try again!")

if _name_ == "_main_":
    main()

