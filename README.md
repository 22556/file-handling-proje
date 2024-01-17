# file-handling-proje
from pathlib import Path  
import os
import shutil

def creatingfolder():
    try:
        name = input("tell your folder name")
        path = Path(name)
        path.mkdir()
        print(f"folder name {name} has been created successfully")
    except Exception as err:
        print("folder already exist")


def readfileandfolder():
    path = Path("")
    items = list(path.rglob("*"))
    for i,v in enumerate(items):
        print(f"{i+1}) {v}")


def updatefolder():
    try:
        readfileandfolder()
        oldname = input("tell which folder you want to update")
        path = Path(oldname)
        if path.exists() and path.is_dir():
            newname = input("tell your new name")
            newpath = Path(newname)
            path.rename(newpath)
            print(f"folder name {oldname} updated to {newname} successfully")
        else:
            print("Error folder does not exist")
    except Exception as err:
        print(f"An error occured as {err}")

def deletefolder():
    try:
        readfileandfolder()
        name = input("tell your folder name that you want to delete")
        path = Path(name)
        if path.exists() and path.is_dir():
            shutil.rmtree(path)
            print("successfully deleted")
        else:
            print("Error folder does not exist")
    except Exception as err:
        print(f"Error as {err}")


print("press 1 for creating a folder")
print("press 2 for reading all items")
print("press 3 for updating a folder")
print("press 4 for deleating a fodler")
print("press 5 for creating a file")
print("press 6 for updating a file")
print("press 7 for reading a file")
print("press 8 for deleting a file")
a = input("tell your input")

if a == "1":
    creatingfolder()
if a == "2":
    readfileandfolder()

if a == "3":
    updatefolder()

if a == "4":
    deletefolder()
