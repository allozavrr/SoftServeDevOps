1) Analyze the structure of the /etc/passwd and /etc/group file, what fields are present in it, what users exist on the system? Specify several pseudo-users, how to define them?

The /etc/passwd file is a colon-separated file that contains the following information:

Username.
Encrypted password.
User ID number (UID)
User's group ID number (GID)
Full name of the user (GECOS)
User home directory.
Login shell.
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/Screenshot%202022-04-13%20at%2016.18.50.png "passwd")

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_16_16_05.png "passwd")

2) What are the uid ranges? What is UID? How to define it?
The user identifier is a number assigned to each user. It is used by the operating system to refer to a user.

3) What is GID? How to define it?
GID. The user’s group identifier number, referring to the user’s primary group. When a user creates a file , the file’s group is set to this group. Typically, the name of the group is the same as the name of the user. User’s secondary groups are listed in the /etc/groups file.

4) How to determine belonging of user to the specific group?

$ groups [username]

$ id [username]

5) What are the commands for adding a user to the system? What are the basic parameters required to create a user?
useradd[-c uidcomment] [-d dir] [-e expire] [-f inactive] [-g gid] [-m [-k skel_dir]] [-s shell] [-u uid[-o]] username dir-- indicates to the user's home directory.

6) How do I change the name (account name) of an existing user?
sudo usermod -l newUsername oldUsername

7) What is skell_dir? What is its structure?
Directory /etc/skel/ (skel is derived from the “skeleton”) is used to initiate home directory when a user is first created. 

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_16_33_44.png "skell_dir")

8) How to remove a user from the system (including his mailbox)?
userdel -r username
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_16_38_22.png "userdel")

9) What commands and keys should be used to lock and unlock a user account?
passwd -l username
passwd -u username
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_16_40_00.png "lock")

10) How to remove a user's password and provide him with a password-free login for subsequent password change?
passwd -e username
chage -l username

11) 
