
# Pondering Paths
### Task 1
The challenge asks to invoke the pwn program using its absolute path.
### My Solve
Flag:pwn.college{MJoHj2bcHojK8KTBbGSAf5hAA88.QX4cTO0wCO5kjNzEzW}
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{MJoHj2bcHojK8KTBbGSAf5hAA88.QX4cTO0wCO5kjNzEzW}
hacker@paths~the-root:~$
```
I launched a terminal and invoked the pwn command from its absolute path typing /pwn to get the flag.
### What I learned 
I familiarised myself with the command line.
### References
Instructions in the pwn.college website.


### Task 2
The challenges asks to execute the run file that is in the challenge directory.
### My Solve 
Flag:pwn.college{oneaYZNtGlkVvfGZkxBaOuXBFwU.QX1QTN0wCO5kjNzEzW}
```
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{oneaYZNtGlkVvfGZkxBaOuXBFwU.QX1QTN0wCO5kjNzEzW}
hacker@paths~program-and-absolute-paths:~$
```
I launched the terminal to type /challenge/run to execute the run file in the challenge directory and hence got the flag.
### What I learned
The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run. We execute the run file using its absolute path.
### References
Instructions in the pwn.college website.


### Task 3
This challenge asks to execute the /challenge/run program from a specific path.
### My Solve 
Flag:pwn.college{Ip9GWT7Xzer_2UTrDfgjik1zkVt.QX2QTN0wCO5kjNzEzW}
```
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /etc/apt/sources.list.d directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /etc/apt/sources.list.d
hacker@paths~position-thy-self:/etc/apt/sources.list.d$  /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Ip9GWT7Xzer_2UTrDfgjik1zkVt.QX2QTN0wCO5kjNzEzW}
hacker@paths~position-thy-self:/etc/apt/sources.list.d$
```
I ran /challenge/run command which told me to switch to a specific directory. I used the cd command to change to that directory and ran /challenge/run in the terminal to get the flag.
### What I learned
Usage of the cd(change directory) command and how it can be used to change the current working directory to an another
specified directory mentioned in its argument.
### References
Instructions in the pwn.college website.


### Task 4
This challenge asks to execute the /challenge/run program from a specific path.
### My Solve
Flag:pwn.college{4V6uaSsrVZmJn95U9F-cc0rVruo.QX3QTN0wCO5kjNzEzW}
```
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/share/doc
hacker@paths~position-elsewhere:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4V6uaSsrVZmJn95U9F-cc0rVruo.QX3QTN0wCO5kjNzEzW}
hacker@paths~position-elsewhere:/usr/share/doc$
```
Exactly same as earlier task.

### What I learned
Usage of the cd(change directory) command and how it can be used to change the current working directory to an another
specified directory mentioned in its argument.
### References
Instructions in the pwn.college website.


### Task 5
Same as Task 4
### My Solve
Flag:pwn.college{8_Px5wBjLUM3RrOVHWHRcUrg9F2.QX4QTN0wCO5kjNzEzW}
```
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/include directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/include
hacker@paths~position-yet-elsewhere:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8_Px5wBjLUM3RrOVHWHRcUrg9F2.QX4QTN0wCO5kjNzEzW}
hacker@paths~position-yet-elsewhere:/usr/include$
```
Exactly same as earlier task.
### What I learned
Usage of the cd(change directory) command and how it can be used to change the current working directory to an another
specified directory mentioned in its argument.
### References
Instructions in the pwn.college website.


### Task 6
The challenge asks to invoke the /challenge/run command using a relative path.
### My Solve
Flag:pwn.college{sQtqbU1q3AeGa57SG458zUVYc2e.QX5QTN0wCO5kjNzEzW}
```
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{sQtqbU1q3AeGa57SG458zUVYc2e.QX5QTN0wCO5kjNzEzW}
hacker@paths~implicit-relative-paths-from-:/$
```
I typed cd / to change the directory to / and typed challenge/run which is a relative path to /challenge/run and hence got the flag.
### What I learned
A relative path is any path that does not start at root (i.e., it does not start with /).
A relative path is interpreted relative to our current working directory (cwd).
Our cwd is the directory that your prompt is currently located at.
### References
Instructions in the pwn.college website.


### Task 7
The challenge asks to invoke the /challenge/run command using . in the relative path.
### My Solve
Flag:pwn.college{80uSc8KPKg6y4IDic4NWJFHetB5.QXwUTN0wCO5kjNzEzW}
```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{80uSc8KPKg6y4IDic4NWJFHetB5.QXwUTN0wCO5kjNzEzW}
hacker@paths~explicit-relative-paths-from-:/$
```
After changing the current working directory to / using cd command, i wrote ./challenge/run which is an explicit relative path to /challenge/run(absolute directory) to get the flag.

### What I learned
In the earlier task, the relative path was "naked": it directly specified the directory to descend into from the current directory.
In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory.
Concept of explicit paths.
### References
Instructions in the pwn.college website.


### Task 8
This challenge asks to run the required /challenge/run command from the /challenge directory using a . in the relative path.
### My Solve
Flag:pwn.college{UPCkMDgq4LMfoGIqwXAUk-pEjg7.QXzMDO0wCO5kjNzEzW}
```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UmTRgxX9XErxGQ2BS2zBMj0MCF-.QXxUTN0wCO5kjNzEzW}
hacker@paths~implicit-relative-path:/challenge$
```
As this challenge required to execute /challenge/run from the challenge directory, i first used cd to change the directory to /challenge. After doing so, typing ./run helped me get the flag.
### What I learned
More clarity in relative paths.
### References
Instructions in the pwn.college website.


### Task 9
In this challenge, the /challenge/run command will write a copy of the flag to the specified file given as argument to the command. Also, this challenge has some constraints:
1.Your argument must be an absolute path.
2.The path must be inside your home directory.
3.Before expansion, your argument must be three characters or less.
### My Solve
Flag:pwn.college{A9SPP_Rlaa-LSrjJWtV3tWbxShD.QXxcTN0wCO5kjNzEzW}
```
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{UPCkMDgq4LMfoGIqwXAUk-pEjg7.QXzMDO0wCO5kjNzEzW}
hacker@paths~home-sweet-home:~$
```
To complete this challenge, I wrote /challenge/run ~/a where ~/a is the argument of a file named a which extends to the absolute path as well is of three characters.
Running the corresponding command, copies the flag to the file. After this, flag is automatically displayed.
### What I learned
The expansion of ~ is an absolute path, and only the leading ~ is expanded. This means, for example, that ~/~ will be expanded to /home/hacker/~ rather than /home/hacker/home/hacker.
### References
Instructions in the pwn.college website.
