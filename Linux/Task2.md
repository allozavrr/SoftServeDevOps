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
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_21_20_48.png "chage")

11) Display the extended format of information about the directory, tell about the information columns displayed on the terminal.

The output from ls –l summarizes the most important information about the file on a single line. If the specified pathname is a directory, ls displays information about every file in that directory (one file per line). It precedes this list with a status line that indicates the total number of file system blocks occupied by files in the directory (in 512-byte). 

The output from ls –a lists all entries including those starting with a period.

Permissions, gid, user, store, mod data and time, directories


![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_21_39_39.png "ls")

12) What access rights exist and for whom (i. e., describe the main roles)? Briefly describe the acronym for access rights.

types of permissions:
User (or user owner) - u
Group (or owner group) - g
Other (everyone else) - o
All users - a (0nly for command)
types of access:
Read - r or 4
Write - w or 2
execute - x or 1

13) What is the sequence of defining the relationship between the file and the user?

If the UID of the file is the same as the UID of the process, the user is the owner of the file
If the GID of the file matches the GID of any group the user belongs to, he is a member of the group to which the file belongs
If neither the UID no the GID of a file overlaps with the UID of the process and the list of groups that the user running it belongs to, that user is an outsider

14) What commands are used to change the owner of a file (directory), as well as the mode of access to the file? Give examples, demonstrate on the terminal.

There are two ways to change privileges in Linux - absolutr and symbolic
chmod
chown

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_21_55_38.png "chmod")
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_01_07.png "chown")

15) What is an example of octal representation of access rights? Describe the umask command.
chmod 461 filename
To give all permission to everyone on the system:
chmod 777 filename

Umask is a C-shell built-in command which allows you to determine or specify the default access mode for new files you create. You may issue the umask command interactively at the command prompt to affect files created during the current session. The umask command is placed in the .bashrc file to be executed automatically whenever a new shell is started, ensuring that the default is the same for each session.

As example:

022  -rw-r--r--  user can read and write file; group can read; others can read
002  -rw-rw-r--  user can read and write file; group can read and write; others can read

16) Give definitions of sticky bits and mechanism of identifier substitution. Give an example of files and directories with these attributes.
Sticky bit is mainly used on folders in order to avoid deletion of a folder and it’s content by other users though they having write permissions on the folder contents. Only owner who created them and the root user can delete folder contents
chmod -t

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_21_57.png "adduser")
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_24_15.png "stickybit")

17) What file attributes should be present in the command script?
All twelve attributes can be represented as bits of a binary number, equal to 1 if the attribute is set, and 0 if not 
The order of the bits is as follows sU | sG | t | rU | wU | xU | rG | wG || xG | rO | wO | xO, where sU is SetUID, sG is SetGID, t is a t attribute (ls dl then the directory is displayed as a file), than three triples of access attributes
