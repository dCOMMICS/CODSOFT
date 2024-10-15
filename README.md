# CODSOFT

To-Do List App
This is a simple and intuitive To-Do List App built using Android Studio. The app allows users to manage their tasks efficiently, with features like adding, editing, deleting, and marking tasks as completed. The app stores tasks locally to ensure persistence across app sessions.


Screenshot of the main task list and task creation screen.

Features
Home Screen: Displays a list of tasks, showing the task title and completion status.
Task Creation: Add new tasks with a title and optional description.
Task Editing: Edit task titles and descriptions with ease.
Task Completion: Mark tasks as completed or active.
Task Deletion: Delete tasks from the list.
Local Data Storage: Tasks are saved locally using SharedPreferences, so your tasks are always available.
User-Friendly Interface: Designed with simplicity and usability in mind.
Screenshots
1. Home Screen
The home screen displays the current task list and allows you to manage tasks.


Main screen displaying tasks with options to add, edit, or delete tasks.

2. Add New Task
Easily add new tasks by filling in a title and optional description.


Add new tasks with a simple and clean input form.

3. Edit Task
Edit existing tasks and modify their details.


Task editing feature with the option to update the title and description.

Installation
Prerequisites:
Android Studio installed on your system.
Java/Kotlin knowledge for Android development.
Steps:
Clone the repository:
bash
Copy code
git clone https://github.com/your-username/todo-list-app.git
Open the project in Android Studio.
Sync the Gradle files and resolve any dependencies.
Run the project on an emulator or an Android device.
Usage
Add Task: Press the floating action button (FAB) on the home screen to add a new task.
Edit Task: Click on any task to edit the title or description.
Mark Task as Completed: Check the box next to the task to mark it as completed.
Delete Task: Use the delete button on the right side of the task to remove it from the list.
Data Persistence: Your tasks will be saved locally, and you'll find them on the app even after closing and reopening.
Code Snippets
Task Model
java
Copy code
public class Task {
    private String title;
    private String description;
    private boolean isCompleted;

    // Constructor, Getters, Setters
    public Task(String title, String description) {
        this.title = title;
        this.description = description;
        this.isCompleted = false;
    }
}
Task RecyclerView Adapter
java
Copy code
public class TaskAdapter extends RecyclerView.Adapter<TaskAdapter.TaskViewHolder> {
    private List<Task> taskList;

    @Override
    public void onBindViewHolder(@NonNull TaskViewHolder holder, int position) {
        Task task = taskList.get(position);
        holder.taskTitle.setText(task.getTitle());
        holder.taskCompleted.setChecked(task.isCompleted());
    }
}
Task Storage using SharedPreferences
java
Copy code
SharedPreferences sharedPreferences = getSharedPreferences("taskData", MODE_PRIVATE);
SharedPreferences.Editor editor = sharedPreferences.edit();
editor.putString("taskTitle", task.getTitle());
editor.apply();
License
This project is licensed under the MIT License - see the LICENSE file for details.
