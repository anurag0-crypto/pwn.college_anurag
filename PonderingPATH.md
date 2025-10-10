# Pondering PATH
### Task 1
In this level, we will have to disrupt the operation of the /challenge/run program. This program will DELETE the flag file using 
the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to us 
Thus, we must make it so that /challenge/run also can't find the rm command.
### My Solve
Flag:pwn.college{sJbr9AG-7fi45ecs_EhiNrcA3jv.QX2cDM1wCO5kjNzEzW}
```
hacker@path~the-path-variable:~$ export PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{sJbr9AG-7fi45ecs_EhiNrcA3jv.QX2cDM1wCO5kjNzEzW}
hacker@path~the-path-variable:~$
```
I simply set the PATH variable to "" and export it so that when /challenge/run runs as a child process, 
it inherits the broken PATH and can't find the rm command. Hence, the flag is not deleted and the challenge gives it to us.
### What I learned
There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs 
corresponding to commands. If we blank out the variable, things go badly.
Like for an example,without a PATH, bash cannot find the ls command.
### References
Instructions in pwn.college website


### Task 2
This level's /challenge/run will run the win command via its bare name, but this command exists in the 
/challenge/more_commands/ directory, which is not initially in the PATH. 
The win command is the only thing that /challenge/run needs, so we have to just overwrite PATH with that one directory.
### My Solve
Flag:pwn.college{gc548tTdS10JGtKFD0sQ64mandJ.QX1cjM1wCO5kjNzEzW}
```
hacker@path~setting-path:~$ export PATH="/challenge/more_commands"
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{gc548tTdS10JGtKFD0sQ64mandJ.QX1cjM1wCO5kjNzEzW}
hacker@path~setting-path:~$
```
I set the PATH variable to the directory /challenge/more_commands which contains the win command and exported it. I ran /challenge/run
to get the flag
### What I learned
If we maintain useful scripts that we want to be able to launch by bare name, it becomes hectic.
However, by adding directories to or replacing directories in this list, we can expose these programs to be launched using their bare name
For example, I set the path to a directory which contains the win command, and then ran /challenge/run to get the flag
### References
Instructions in pwn.college website


### Task 3
This challenge requires us to find where the win command is located and then access a flag file in the same directory using the 
which command.
### My Solve
Flag:pwn.college{Mlj1oYN6yzTRMr1Ov-sNoOIDENU.01NzEzNxwCO5kjNzEzW}
```
hacker@path~finding-commands:~$ which win
/challenge/paths/10739/win
hacker@path~finding-commands:~$ cd /challenge/paths/10739
hacker@path~finding-commands:/challenge/paths/10739$ ls
flag  win
hacker@path~finding-commands:/challenge/paths/10739$ cat flag
pwn.college{Mlj1oYN6yzTRMr1Ov-sNoOIDENU.01NzEzNxwCO5kjNzEzW}
hacker@path~finding-commands:/challenge/paths/10739$
```
I simply ran which win to find the location of the win command. I changed the directory to /challenge/paths/10739 which contains the win
command. I ran ls to list out all the files in that directory. The flag file had it's filename as flag,so I ran cat flag to display
the flag.
### What I learned
The which command can be precisely used to find the location of the command in its argument.
Mirroring what the shell does when searching for commands, which looks at each directory in $PATH in order and 
prints the first file it finds whose name matches the argument we passed.
### References
Instructions in pwn.college website


### Task 4
In this challenge,the win command does not exist. We need to make a shell script called win, add its location to the PATH, and 
enable /challenge/run to find it.
### My Solve
Flag:pwn.college{g-LGQ-f7NBzr33wtX0N3uit66PN.QX2cjM1wCO5kjNzEzW}
```
hacker@path~adding-commands:~$ mkdir ~/my_scripts
hacker@path~adding-commands:~$ echo '#!/bin/bash
> read flag < /flag
> echo $flag' > ~/my_scripts/win
hacker@path~adding-commands:~$ chmod +x ~/my_scripts/win
hacker@path~adding-commands:~$ export PATH="/home/hacker/my_scripts"
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{g-LGQ-f7NBzr33wtX0N3uit66PN.QX2cjM1wCO5kjNzEzW}
```
I started this challenge by making a new directory /my_scripts using the mkdir command, from the home/hacker directory(~ is the short form
of the same). I typed echo '#!/bin/bash to create a shebang for the shell script.  I used the read builtin to take the output of /flag
as input and store it in a variable called flag, and typed  echo $flag' > ~/my_scripts/win to redirect the output of the echo command
to the shell script. Then, I granted the executable permission to the shell script via chmod +x ~/my_scripts/win. Then,I exported and set
the PATH variable pointing to the shell script and ran /challenge/ran to get the flag.
### What I learned
Problem Solving
### References
Instructions in pwn.college website


### Task 5
This challenge is almost the same as the first challenge in this module. Again, this challenge will delete the flag using the rm command.
But unlike before, it will not print anything out.
### My Solve
Flag:pwn.college{Ie0sMXkq9kuSsKEvSI_IBmjWLGo.QX3cjM1wCO5kjNzEzW}
```
hacker@path~hijacking-commands:~$ mkdir ~/my_commands
mkdir: cannot create directory ‘/home/hacker/my_commands’: File exists
hacker@path~hijacking-commands:~$ echo '#!/bin/bash
> cat /flag' > ~/my_commands/rm
hacker@path~hijacking-commands:~$ chmod +x ~/my_commands/rm
hacker@path~hijacking-commands:~$ export PATH="/home/hacker/my_commands:$PATH"
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/my_commands/rm. Executing!
pwn.college{Ie0sMXkq9kuSsKEvSI_IBmjWLGo.QX3cjM1wCO5kjNzEzW}
hacker@path~hijacking-commands:~$
```
I created a fake rm command in this challenge which displays the flag using cat command rather than removing it. I ran 
export PATH="/home/hacker/my_commands:$PATH" to add the commands in the new directory as well retain the commands in the original
path(for example:cat,echo), this also ensures that the fake rm command is found first and executed and the actual rm command is
not executed at all. As the shell goes from directories left to right, the mentioned path containing the fake rm command is found first.
Then, as usual I gave executable permissions to the script and ran /challenge/run to execute the fake rm command to print the flag.
### What I learned
Problem solving and hijacking commands.
### References
Instructions in pwn.college website.












hacker@path~adding-commands:~$























