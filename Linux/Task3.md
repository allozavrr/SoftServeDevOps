1. How many states could has a process in Linux?
Running or Runnable (R)
Uninterruptible Sleep (D)
Interruptable Sleep (S)
Stopped (T)
Zombie (Z)

2. Examine the pstree command. Make output (highlight) the chain (ancestors) of the current process.
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_36_03.png "pstree")

3. What is a proc file system?
Proc file system (procfs) is virtual file system created on fly when system boots and is dissolved at time of system shut down.

It contains useful information about the processes that are currently running, it is regarded as control and information center for kernel.

The proc file system also provides communication medium between kernel space and user space.

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_39_17.png "proc")

4. Print information about the processor (its type, supported technologies, etc.).
lscpu
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_41_59.png "lscpu")

5. Use the ps command to get information about the process. The information should be as follows: the owner of the process, the arguments with which the process was launched for execution, the group owner of this process, etc.
ps aux | head
![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_45_42.png "ps aux")

6. How to define kernel processes and user processes?

Kernel processes or threads do not have their own address space, they operate within kernel address space only. And they may be started before the kernel has started any user process (e.g. init). When managing processes, it is easy to recognize the kernel processes because they have a name that is between square brackets.

7. Print the list of processes to the terminal. Briefly describe the statuses of the processes. What condition are they in, or can they be arriving in?

Item Description
USER	User login name
PID	Process ID
PPID	Parent process ID
C	CPU utilization of process
STIME	Start time of process
TTY	Controlling workstation for the process
TIME	Total execution time for the process
CMD	Command

ps -ef

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_22_56_35.png "ps -ef")

8. Display only the processes of a specific user.

ps --user username

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_23_01_33.png "ps --user")

9. What utilities can be used to analyze existing running tasks (by analyzing the help for the ps command)?

If you wish to display processes in BSD format, execute

ps aux
-a flag stands for all processes

-xwill display all processes even those not associated with the current tty

To view a full format listing run

ps -ef 

https://www.journaldev.com/24613/linux-ps-command - manual

10. What information does top command display?

top command is used to show the Linux processes. It provides a dynamic real-time view of the running system. Usually, this command shows the summary information of the system and the list of processes or threads which are currently managed by the Linux Kernel.

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_13_04_2022_23_11_06.png "top")

11. Display the processes of the specific user using the top command.

top -U username



