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

![alt text](https://github.com/allozavrr/SoftServeDevOps/blob/main/Linux/Screens/VirtualBox_Ubuntu_14_04_2022_00_35_16.png "top -U")

12. What interactive commands can be used to control the top command? Give a couple of examples.

-d [secs.tenths]	Delay time interval	Prompts you to specify the delay before updating the screen, overriding the default value. The value is in seconds. The command accepts fractional seconds but doesn't accept negative numbers.
-e [k | m | g | t | p]	Toggle task memory scaling	Allows you to change top task area memory scaling. The available scaling options are k (kibibytes), m (mebibytes), g (gibibytes), t (tebibytes), p (pebibytes).


13. Sort the contents of the processes window using various parameters (for example, the amount of processor time taken up, etc.)

To sort all Linux running processes by Process ID, press M and T keys.

To sort all Linux running processes by running time, press M and T keys.
Press ‘c‘ option in running top command will display the absolute path of the running process.
By default screen refresh interval is set to 3.0 seconds, the same can be changed by pressing the ‘d‘ option in running the top command to set desired interval time.
To sort all running processes by CPU utilization, simply press Shift+P key.
To list the load information of your CPU cores, simply press 1 to list the CPU core details.
Press 'i' to get the list of idle/sleeping processes.
Press the ‘h‘ option to obtain the top command help.
The output of the top command keeps refreshing until you press ‘q‘. With the below command, it will automatically exit after 10 repetitions.
You can kill a process after finding the PID of the process by pressing the ‘k‘ option in running the top command without closing the top window as shown below signal 15 for SIGTERM 9 for SIGKILL.

14. Concept of priority, what commands are used to set priority?

change the default priority that was assigned to the process when it was started you can do using the nice and renice commands 

nice - to start a process with an adjusted priority 

renice - to change the priority for a currently active process 

Alternatively, you can use the r command from the top utility to change the priority of a currently running process 

When using nice or renice to adjust process priority, you can select from values ranging from 20 to 19 The default niceness of a process is set to 0 (which results in the priority value of 20 
By applying a negative niceness, you can increase the priority 

15. Can I change the priority of a process using the top command? If so, how?

To renice a running process from top, type r and prompt for the PID of the process you want to renice . After entering the PID, you are prompted for the nice value you want to use. Enter a positive value to increase process priority or a negative value to decrease process priority.

16. Examine the kill command. How to send with the kill command process control signal? Give an example of commonly used signals.
kill command in Linux (located in /bin/kill), is a built-in command which is used to terminate processes manually. kill command sends a signal to a process which terminates the process.

Signals can be specified in three ways:
By number (e.g. -5)
With SIG prefix (e.g. -SIGkill)
Without SIG prefix (e.g. -kill)

A PID of -1 is very special as it indicates all the processes except kill and init, which is the parent process of all processes on the system.

kill pid

17. Commands jobs, fg, bg, nohup. What are they for? Use the sleep, yes command to demonstrate the process control mechanism with fg, bg.




