1) Analyze the structure of the /etc/passwd and /etc/group file, what fields are present in it, what users exist on the system? Specify several pseudo-users, how to define them?

The /etc/passwd file is a colon-separated file that contains the following information:
Username.
Encrypted password.
User ID number (UID)
User's group ID number (GID)
Full name of the user (GECOS)
User home directory.
Login shell.

mark:x:1001:1001:mark,,,:/home/mark:/bin/bash
[--] - [--] [--] [-----] [--------] [--------]
|    |   |    |     |         |        |
|    |   |    |     |         |        +-> 7. Login shell
|    |   |    |     |         +----------> 6. Home directory
|    |   |    |     +--------------------> 5. GECOS
|    |   |    +--------------------------> 4. GID
|    |   +-------------------------------> 3. UID
|    +-----------------------------------> 2. Password
+----------------------------------------> 1. Username

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_16_16_05.png "passwd")
