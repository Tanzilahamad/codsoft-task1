#include <iostream>
#include <vector>
#include <string>
using namespace std;


struct Task {
    string description;
    bool isCompleted;
};


void displayMenuu() {
    cout << "\nTo-Do List Manager\n";
    cout << "1. Add Task to list\n";
    cout << "2. View Tasks\n";
    cout << "3. Mark Task as Completed\n";
    cout << "4. Remove Task\n";
    cout << "5. Exit\n";
    cout << "Enter your choice: ";
}


void addTask(vector<Task>& tasks) {
    cout << "Enter the task description: ";
    string description;
    cin.ignore();
    getline(cin, description);
    tasks.push_back({description, false});
    cout << "Task added successfully.\n";
}


void viewTasks(const vector<Task>& tasks) {
    if (tasks.empty()) {
        cout << "No tasks to display.\n";
        return;
    }
    cout << "\nTasks:\n";
    for (size_t i = 0; i < tasks.size(); ++i) {
        cout << i + 1 << ". " << tasks[i].description;
        cout << " [" << (tasks[i].isCompleted ? "Completed" : "Pending") << "]\n";
    }
}


void markTaskCompleted(vector<Task>& tasks) {
    viewTasks(tasks);
    if (tasks.empty()) return;
    cout << "Enter the task number to mark as completed: ";
    size_t taskNumber;
    cin >> taskNumber;
    if (taskNumber >= 1 && taskNumber <= tasks.size()) {
        tasks[taskNumber - 1].isCompleted = true;
        cout << "Task marked as completed.\n";
    } else {
        cout << "Invalid task number.\n";
    }
}

void removeTask(vector<Task>& tasks) {
    viewTasks(tasks);
    if (tasks.empty()) return;
    cout << "Enter the task number to remove: ";
    size_t taskNumber;
    cin >> taskNumber;
    if (taskNumber >= 1 && taskNumber <= tasks.size()) {
        tasks.erase(tasks.begin() + taskNumber - 1);
        cout << "Task removed successfully.\n";
    } else {
        cout << "Invalid task number.\n";
    }
}

int main() {
    vector<Task> tasks;
    int ch;

    do {
        displayMenu();
        cin >> ch;

        switch (ch) {
            case 1:
                addTask(tasks);
                break;
            case 2:
                viewTasks(tasks);
                break;
            case 3:
                markTaskCompleted(tasks);
                break;
            case 4:
                removeTask(tasks);
                break;
            case 5:
                cout << "Exiting the program. Goodbye!\n";
                break;
            default:
                cout << "Invalid choice. Please try again.\n";
        }
    } while (ch!= 5);

    return 0;
}
