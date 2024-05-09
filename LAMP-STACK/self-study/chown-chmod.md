## **Linux File Permission and Ownership**

### **Introduction**

Linux is a multi-user operating system. In an enterprise system, there would be multiple users accessing the same system. But if any user could access and modify all files belonging to other users or system files, this would certainly be a security risk.

This is why UNIX and thus Linux (Linux is a Unix-like system) has built-in security measure in place. This ensures that a file or directory can be accessed, modified or executed by only desired users. Which file would be accessed by which user is decided by two factors in Linux:

- File ownership
- File permission



### 1. **File ownership in Linux**

Linux assigns ownership of files and directories to three entities: the user, group, and other. Let's understand what each of these entities represents:

 - **User:** The user refers to the individual who owns the file. This is typically the user account that created the file.

- **Group:** The group is a collection of user accounts. In Linux, each user account is associated with one or more groups. The group ownership of a file determines the permissions granted to all the members of that group.

- **Other:** Other refers to all users who are neither the owner nor a member of the group associated with the file. The permissions granted to the "other" category apply to all users who fall into this category.

To change the ownership of a file, you can use the command chown. You may easily guess that chown stands for change owner.

You can change the user owner of a file in the following manner:

```bash
chown <new_user_name> <filename>
```

If you want to change the user as well as group, you can use chown command like this:

```bash
chown <new_user_name>:<new_user_group> <filename>
```

If you just want to change the group, you can either use chown command in this manner:

```bash
chown :<new_user_group> <filename>
```

or use chgrp command specifically used for changing group owner of a file or directory. You can guess that chgrp stands for change group.

```bash
chgrp <new_user_group> <filename>
```

In our example so far, if you want to change the user owner and group to root, you can use the chown command like this:

```bash
sudo chown root:root agatha.txt
```

This will change the ownership of the file to root for both user and the group.

```bash
-rw-rw---- 1 root root 457 Aug 10 11:55 agatha.txt
```

### 2. **File permission in Linux**

Linux provides three basic permissions that can be assigned to files and directories: read, write, and execute. Let's examine what each of these permissions entails:

- **Read:** The read permission allows users to view the contents of a file or list the contents of a directory. For directories, read permission enables users to navigate through the directory structure.

- **Write:** The write permission grants users the ability to modify the contents of a file or add, delete, and rename files within a directory. For directories, write permission allows users to create or delete files and subdirectories.

- **Execute:** The execute permission enables users to execute a file if it is a program or script. For direct

You can use chmod command for changing the permissions on a file in Linux. There are two ways to use the chmod command:

- Absolute mode
- Symbolic mode

### Using chmod in absolute mode

In the absolute mode, permissions are represented in numeric form (octal system to be precise). In this system, each file permission is represented by a number.

- r (read) = 4
- w (write) = 2
- x (execute) = 1
- – (no permission) = 0

With these numeric values, you can combine them and thus one number can be used to represent the entire permission set.

Suppose you want to change the file permission on agatha.txt so that everyone can read and write but no one can execute it? In that case, you can use the chmod command like this:

```bash
chmod 666 agatha.txt
```

If you list agatha.txt now, you’ll see that the permission has been changed.

```bash
-rw-rw-rw- 1 abhishek abhishek 457 Aug 10 11:55 agatha.txt
```

### Using chmod in symbolic mode

The problem with the absolute mode is that you should always provide three numbers for all the three owners even if you want to change the  permission set for just one owner.

This is where you can use the symbolic mode with chmod command.

In symbolic mode, owners are denoted with the following symbols:

- u = user owner
- g = group owner
- o = other
- a = all (user + group + other)

The symbolic mode uses mathematical operators to perform the permission changes:

- + for adding permissions
- – for removing permissions
- = for overriding existing permissions with new value
Now that you know let’s see how to use chmod command in symbolic mode.

 if you want to add execute permission for group owner, you can use chmod command like this:

 ```bash
 chmod g+x agatha.txt
 ```
If you look at the permissions on this file now, you’ll see that execute permission has now been added: 

```bash
-rw-rwxrw- 1 abhi itsfoss 457 Aug 10 11:55 agatha.txt
```

You can also combine multiple permission changes in one command. Suppose you want to remove the read and write permission and add execute permissions for Other. You also want to add execute permission for the User owner. You can do all of it one single command:

```bash
chmod o-rw+x,u+x agatha.txt
```
The resulting permissions would be like this:

```bash
-rwxrwx--x 1 abhi itsfoss 457 Aug 10 11:55 agatha.txt
```

If you want to change the permissions for all three kinds of users at the same time, you can use it in the following manner:

```bash
chmod a-x agatha.txt
```

This will remove the execute permission for everyone.

```bash
-rw-rw---- 1 abhi itsfoss 457 Aug 10 11:55 agatha.txt
```

###### Reference 1: https://linuxhandbook.com/linux-file-permissions/

###### Reference 2: https://www.linkedin.com/pulse/understanding-linux-file-ownership-permissions/
