# Application-Opener-GUI-in-Python
->This is a GUI developed in python that provides functionality to open a number of programs/applications to be seleced via filedialog box from your desktop and shows them as a list. You can then open these certain number of applications by just one click on the button provided on GUI.


-> I have created this in Visual Studio 2019 


-> Here is the source code in .txt format in case you are interested:


import tkinter as tk 
from tkinter import filedialog, Text
import os


root = tk.Tk()
apps = []


def addApp():

    for widget in frame.winfo_children():
        widget.destroy()

    filename=filedialog.askopenfilename(initialdir="/", title="Select File",
                                        filetypes=(("executables","*.exe"),("all files", "*.*")))

    apps.append(filename)
    print(filename)

    for app in apps:
        label = tk.Label(frame, text=app, bg="blue")
        label.pack()

def runapps():
    for app in apps:
        os.startfile(app)



canvas = tk.Canvas(root, height=700, width=700, bg="#263042")
canvas.pack()

frame = tk.Frame(root, bg="yellow")
frame.place(relwidth=0.8, relheight=0.8, relx=0.1, rely=0.1)

openFile = tk.Button(root, text="search programs", padx=80,
                     pady=5, fg="white", bg="red", command=addApp) 
openFile.pack()


runapps = tk.Button(root, text="open application", padx=10,
                     pady=5, fg="white", bg="red", command="runapps") 
runapps.pack()




root.mainloop()
