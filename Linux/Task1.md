1) Log in to the system as root.

sudo su


![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_06_04_2022_15_47_46.png "sudo su")

2) Use the passwd command to change the password. Examine the basic  parameters of the command. What system file does it change *?

ls -lt


![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_12_04_2022_01_50_45.png "ls -lt")

/etc/shadow


![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_12_04_2022_01_51_28.png "/etc/shadow")


3) Determine the users registered in the system, as well as what commands they  execute. What additional information can be gleaned from the command  execution? 
who
w


4) Change personal information about yourself. 
chfn

5) Become familiar with the Linux help system and the man and info commands.  Get help on the previously discussed commands, define and describe any two  keys for these commands. Give examples. 
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_06_04_2022_15_54_44.png "man")
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_06_04_2022_15_54_25.png "man")
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_06_04_2022_15_53_31.png "man man")


6) Explore the more and less commands using the help system. View the contents  of files .bash* using commands. 


7) * Describe in plans that you are working on laboratory work 1. Tip: You should  read the documentation for the finger command. 
su
chmod 755 .plan 
chmod .
finger -l
echo "I'm working on labaratory work 1" > ~/.plan
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_11_04_2022_14_41_35.png "echo")



8) * List the contents of the home directory using the ls command, define its files  and directories. Hint: Use the help system to familiarize yourself with the ls  command. 
ls -lh
d is the directory
- is file 
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_12_04_2022_02_17_09.png "ls -lh")

Task1.Part2 
1) Examine the tree command. Master the technique of applying a template, for  example, display all files that contain a character c, or files that contain a  specific sequence of characters. List subdirectories of the root directory up to  and including the second nesting level. 

sudo apt-get install tree
tree -df

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_14_38_01.png "tree")


2) What command can be used to determine the type of file (for example, text or  binary)? Give an example. 

file

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_14_42_55.png "file")


3) Master the skills of navigating the file system using relative and absolute paths.  How can you go back to your home directory from anywhere in the filesystem?

An absolute path is defined as specifying the location of a file or directory from the root directory(/). In other words,we can say that an absolute path is a complete path from start of actual file system from / directory.

Relative path is defined as the path related to the present working directly(pwd). It starts at your current directory and never starts with a / .

Back to your home directory from anywhere - cd ~

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_14_50_55.png "path")
 
4) Become familiar with the various options for the ls command. Give examples  of listing directories using different keys. Explain the information displayed on  the terminal using the -l and -a switches. 

ls -la

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_14_53_36.png "ls")

5) Perform the following sequence of operations: 
- create a subdirectory in the home directory; 

- in this subdirectory create a file containing information about directories  located in the root directory (using I/O redirection operations); 

- view the created file; 

- copy the created file to your home directory using relative and absolute  addressing.
 
- delete the previously created subdirectory with the file requesting removal; - delete the file copied to the home directory. 

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_10_26.png "create")

6) Perform the following sequence of operations: 
- create a subdirectory test in the home directory;
- copy the .bash_history file to this directory while changing its name to  labwork2; 
- create a hard and soft link to the labwork2 file in the test subdirectory; - how to define soft and hard link, what do these 
concepts; 
- change the data by opening a symbolic link. What changes will happen and  why 
- rename the hard link file to hard_lnk_labwork2; 
- rename the soft link file to symb_lnk_labwork2 file; 
- then delete the labwork2. What changes have occurred and why? 

7) Using the locate utility, find all files that contain the squid and traceroute  sequence. 
updatedb
locate squid
locate traceroute

sudo apt update
sudo apt install mlocate
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_19_55.png "locate")

8) Determine which partitions are mounted in the system, as well as the types of  these partitions.

findmnt 

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_22_21.png "findmnt")

9) Count the number of lines containing a given sequence of characters in a given  file. 

wc /proc/cpuinfo 

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_24_14.png "wc")

10) Using the find command, find all files in the /etc directory containing the  host character sequence. 

find /etc -name 'host*' -printf0 | wc -l --files0-from=-

11) List all objects in /etc that contain the ss character sequence. How can I  duplicate a similar command using a bunch of grep?
sudo find /etc -name 'ss*' | wc -l --files0-from=-

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_28_57.png "wc")
 
12) Organize a screen-by-screen print of the contents of the /etc directory. Hint:
You must use stream redirection operations.

sudo ls /etc > temp.txt
cat temp.txt

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_36_32.png ">")
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_35_12.png "result")

13) What are the types of devices and how to determine the type of device? Give examples.
Linux recognizes two different kinds of device: random-access block devices (such as disks), and character devices (such as tapes and serial lines) , some of which may be serial, and some random-access.

All devices are represented by files called special files that are located in/dev directory. Thus, device files and other files are named and accessed in the same way. A 'regular file' is just an ordinary data file in the disk. A 'block special file' represents a device with characteristics similar to a disk (data transfer in terms of blocks). A 'character special file' represents a device with characteristics similar to a keyboard (data transfer is by stream of bits in sequential order).

ls -la /dev

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_43_51.png "dev")

14) How to determine the type of file in the system, what types of files are there?

There are types of files are available in Linux with 3 Major categories. 

Regular File
Directory File
Special Files (There are five types of files in the special category)
Link File
Character Device File
Socket File
Named Pipe File
Block File

“-” refers to the identification symbol for the regular file
“d” refers to the directory
“l” refers to the link

Use ls command 

15) List the first 5 directory files that were recently accessed in the /etc directory.

ls -lht | head -6

-l outputs in a list format

-h makes output human readable (i.e. file sizes appear in kb, mb, etc.)

-t sorts output by placing most recently modified file first

head -6 will show 5 files because ls prints the block size in the first line of output.

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_15_51_26.png "6")
