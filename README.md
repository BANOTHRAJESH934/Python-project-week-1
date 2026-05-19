# Python-project-week-1
To-Do List Application using Python Tkinter A simple desktop-based To-Do List application developed using Python and Tkinter GUI library. This project allows users to: ✔ Add new tasks ✔ Mark tasks as completed ✔ Delete tasks from the list ✔ Manage daily activities with a simple user interface
code:
import tkinter as tk

tasks = []

def add_task():
    task = entry.get()
    if task != "":
        tasks.append(task)
        listbox.insert(tk.END, task)
        entry.delete(0, tk.END)

def delete_task():
    selected = listbox.curselection()
    if selected:
        index = selected[0]
        listbox.delete(index)
        tasks.pop(index)

def mark_done():
    selected = listbox.curselection()
    if selected:
        index = selected[0]
        task = listbox.get(index)
        listbox.delete(index)
        listbox.insert(index, task + " ✔")

root = tk.Tk()
root.title("To-Do List")

entry = tk.Entry(root, width=30)
entry.pack()

btn_add = tk.Button(root, text="Add Task", command=add_task)
btn_add.pack()

btn_done = tk.Button(root, text="Mark Done", command=mark_done)
btn_done.pack()

btn_delete = tk.Button(root, text="Delete Task", command=delete_task)
btn_delete.pack()

listbox = tk.Listbox(root, width=40)
listbox.pack()

root.mainloop()
