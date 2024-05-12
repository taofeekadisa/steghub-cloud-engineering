## **Nano Editor in Linux**

### **Introduction**

Nano is a command-line text editor that comes pre-installed with most Linux distributions. It’s designed to be user-friendly, with a simple interface that resembles popular graphical text editors. Nano provides essential editing features, making it ideal for quick edits, creating configuration files, or writing scripts directly in the terminal.

### **Working with Nano Text Editor**

### 1. Create and Open a New File in Nano Editor

This command will open a new file with new_filename as shown in the output. In case the file already exists it will open the same and in case the file is not there in the current directory it will create a new one. At the bottom of the window, there is a list of shortcut keys for nano.

```bash
nano new_filename
```

### 2. Save a file in Nano Editor

It will ask you for the filename. In case, you want to save the changes to a new file or want to create a new file then change the name else keep the name same.

```bash
press Ctrl + o
```
As soon as you will press enter key, then In case, you have changed the name of the file then it will save the file with a new name and if not then it will save the changes to the current file.

### 3. Cut and Past in Nano Editor

To cut paste in a file. Ctrl+o is used to cut and Ctrl+u is used to paste the text. To cut and paste a whole line. Move to the line which you want to cut then press Ctrl+k. Now the line is moved to clipboard, To paste it, go to the position where you want to paste and then press Ctrl+u.

To cut and paste the selected text. Select the text which you want to cut then press Ctrl+k. Now the text is moved to clipboard. To paste it, go to the position where you want to paste and then press Ctrl+u.

### 4. Search in Nano Editor

To search a word in a file Ctrl+w is used. Press Ctrl+w It will ask for a word to search for. Enter the word It will search for the word and will place the cursor in the first letter of the first occurrence of the word.

### 5. Spelling Check in Nano Editor

To enable spell check in nano. First, install the spell check package.

```bash
sudo apt install spell
```

###### Reference 2: https://www.geeksforgeeks.org/nano-text-editor-in-linux/