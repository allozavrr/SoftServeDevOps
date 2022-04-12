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

2) What command can be used to determine the type of file (for example, text or  binary)? Give an example. 

find fylename -type

3) Master the skills of navigating the file system using relative and absolute paths.  How can you go back to your home directory from anywhere in the filesystem?
 cd /
 
4) Become familiar with the various options for the ls command. Give examples  of listing directories using different keys. Explain the information displayed on  the terminal using the -l and -a switches. 

ls -la

5) Perform the following sequence of operations: 
- create a subdirectory in the home directory; 

cd Home
mkdir temp

- in this subdirectory create a file containing information about directories  located in the root directory (using I/O redirection operations); 
cd temp
ls -la / > test.out 

- view the created file; 
cat test.out

- copy the created file to your home directory using relative and absolute  addressing.
 cp Home
 

- delete the previously created subdirectory with the file requesting removal; - delete the file copied to the home directory. 
rmdir
cd
rm

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

8) Determine which partitions are mounted in the system, as well as the types of  these partitions.

findmnt /home

9) Count the number of lines containing a given sequence of characters in a given  file. 

wc /proc/cpuinfo 

10) Using the find command, find all files in the /etc directory containing the  host character sequence. 

find /etc -name 'host*' -printf0 | wc -l --files0-from=-

11) List all objects in /etc that contain the ss character sequence. How can I  duplicate a similar command using a bunch of grep?
find /etc -name 'ss*' -printf0 | wc -l --files0-from=-
grep "ss*" /etc | wc -l
 
12) 








Symbolic links. A file in Linux can have multiple names or "hard links". 
A hard link is just another name for the original file. It is written in the inode of the source file. Once a hard link is created, it is impossible to distinguish between where the original file name is and where the link is. If you delete one of these files (more precisely one of these names), then the file is still saved on disk (as long as it has at least one link name). 
Example: 
[globus@fedora lab1]$ ln lab1.txt link_on_lab1 
There is another type of links in Linux, so called symbolic links. These links can also be considered as additional filenames, but at the same time they are represented as separate files - files such as symbolic links. Unlike hard links, symbolic links can point to files located in a different file system, such as a mountable medium, or even on another computer. If the original file is deleted, the symbolic link is not removed, but is useless. 
To create a symbolic link, use the ln command with the additional -s option:  
ln -s name_of_file_or_directory_link_name

