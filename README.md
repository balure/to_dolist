# todo_list.py

tasks = []

def show_menu():
    print("\n--- To-Do List ---")
    print("1. View tasks")
    print("2. Add task")
    print("3. Remove task")
    print("4. Exit")

def view_tasks():
    if not tasks:
        print("No tasks yet.")
    else:
        print("Your tasks:")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")

def add_task():
    task = input("Enter a new task: ")
    tasks.append(task)
    print(f"Added: {task}")

def remove_task():
    view_tasks()
    if tasks:
        try:
            num = int(input("Enter task number to remove: "))
            removed = tasks.pop(num - 1)
            print(f"Removed: {removed}")
        except (ValueError, IndexError):
            print("Invalid task number.")

def main():
    while True:
        show_menu()
        choice = input("Choose an option (1-4): ")
        if choice == "1":
            view_tasks()
        elif choice == "2":
            add_task()
        elif choice == "3":
            remove_task()
        elif choice == "4":
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please enter 1-4.")

if __name__ == "__main__":
    main()
