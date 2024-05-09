## **Visual Editor in Linux**

### **Introduction**

The vi editor is elaborated as visual editor. It is installed in every Unix system. In other words, it is available in all Linux distros. It is user-friendly and works same on different distros and platforms. It is a very powerful application. An improved version of vi editor is vim.

The vi editor has two modes:

- **Command Mode** : In command mode, actions are taken on the file. The vi editor starts in command mode. Here, the typed words will act as commands in vi editor. To pass a command, you need to be in command mode.

- **Insert Mode** : In insert mode, entered text will be inserted into the file. The Esc key will take you to the command mode from insert mode.

By default, the vi editor starts in command mode. To enter text, you have to be in insert mode, just type 'i' and you'll be in insert mode. Although, after typing i nothing will appear on the screen but you'll be in insert mode. Now you can type anything. To exit from insert mode press Esc key, you'll be directed to command mode.

### **Lunch VI Test Editor**

First, you need to launch the VI editor to begin working on it. To launch the editor, open your Linux terminal and then type:

```bash
vi <filename_NEW> or <filename_EXISTING>
```

### **VI Editing Commands**

You need to be in the command mode to run editing commands in the VI editor. VI is case-sensitive. Hence, make sure you use the commands in the correct letter case. Also, make sure you type the right command to avoid undesired changes. Below are some of the essential commands to use in VI.

i – Inserts at cursor (gets into the insert mode)

a – Writes after the cursor (gets into the insert mode)

A – Writes at the ending of a line (gets into the insert mode)

o – Opens a new line (gets into the insert mode)

ESC – Terminates the insert mode

u – Undo the last change

U – Undo all changes of the entire line

D – Deletes the content of a line after the cursor

R – Overwrites characters from the cursor onwards

r – Replaces a character

s – Substitutes one character under the cursor and continue to insert

S – Substitutes a full line and start inserting at the beginning of a line

~ – Changes a character’s case

dd – Deletes the line

3dd – Deletes 3 lines

dw – Deletes a word

4dw – Deletes 4 words

x – Deletes a character at the cursor

cw – Changes the word

### **Commands for Moving within a File**

For moving within a file, you should be in the command mode. Also, arrow keys can be used to navigate. Below are the commands used to navigate within a file.

k – Moves cursor up

j – Moves cursor down

l – Moves cursor right

h – Moves cursor left

### **Commands for Saving and Closing a File**

To exit the text editor and save the changes to a file, you need to be in the command mode. Below are the commands to use for saving and closing a file in the editor.

Shift+zz – Saves a file and exits

:w – Saves a file and keeps the file open

:q – Exits without saving

:wq – Saves a file and quits

###### Reference 1: https://www.javatpoint.com/vi-editor

###### Reference 2: https://www.linuxjournal.com/content/how-use-vi-editor-linux