# Lab-Commands

# **Day-1**

### Various ways to find your current shell

```bash
echo $SHELL 

echo $0

#The ps (process status) command provides a snapshot of the currently running processes
ps

#Viewing the /etc/passwd File
cat /etc/passwd
or
grep `whoami` /etc/passwd
```

### **List shells in your Linux**

```bash
cat /etc/shells
```

- Users can change shell to any other shell listed in /etc/shells/.
- The root account can be used to change any other user login shell.
- If an account has a restricted login shell, then only the root can change that user’s shell.

### Create a User and change his default shell to

```bash
#Create a user
sudo adduser test

#Find his default shell
grep test /etc/passwd

#Typical output
test:x:1001:1001:,,,:/home/test:/bin/bash

#Change his shell to **sh**
sudo chsh -s /bin/sh test

#Confirm the changes
grep test /etc/passwd

#Typical output
test:x:1001:1001:,,,:/home/test:/bin/sh

```