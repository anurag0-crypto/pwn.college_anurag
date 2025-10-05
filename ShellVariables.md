# Shell Variables
### Task 1
This challenge asks to obtain the flag which has been stored in a variable called FLAG.
### My Solve
Flag:pwn.college{gD3HDJGRmNbhc4m4CyW7KoTe-vq.QX3UTN0wCO5kjNzEzW}
```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{gD3HDJGRmNbhc4m4CyW7KoTe-vq.QX3UTN0wCO5kjNzEzW}
hacker@variables~printing-variables:~$
```
I simply ran echo $FLAG to print it as FLAG is a variable.
### What I learned
We can print out variables by echo command by prepending them with a $.
### My References
Instructions in pwn.college website.


### Task 2
This challenge asks to set the value of variable PWN to COLLEGE.
### My Solve
Flag:pwn.college{k_70KnrYX5SJuyOfC7-QL1yLDWE.QX5UTN0wCO5kjNzEzW}
```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{k_70KnrYX5SJuyOfC7-QL1yLDWE.QX5UTN0wCO5kjNzEzW}
hacker@variables~setting-variables:~$
```
I simply ran PWN=COLLEGE with no space in between to get the flag.
### What I learned
Assignment of variables.
### My References
Instructions in pwn.college website


### Task 3
This challenge asks to set the value of variable PWN to COLLEGE YEAH
### My Solve
Flag:pwn.college{c7OSkD9xsRhoAYIaViNQisYJLqE.QXwYTN0wCO5kjNzEzW}
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{c7OSkD9xsRhoAYIaViNQisYJLqE.QXwYTN0wCO5kjNzEzW}
hacker@variables~multi-word-variables:~$
```
I simply assign PWN="COLLEGE YEAH" as there cannot be any spaces in assignment of variables. As it is multi word value, I had to enclose the value in double quotation.
### What I learned
When the shell sees a space, it ends the variable assignment and interprets the next word. So, for assigning multi word
values to variables, we need to quote it.
### My References
Instructions in pwn.college website


### Task 4
This challenge asks to assign PWN to value COLLEGE and export it and assign COLLEGE to value PWN and not export it.
### My Solve
Flag:pwn.college{YDeMPLzeLXlLiOhxG9GQjpubYql.QXyYTN0wCO5kjNzEzW}
```
hacker@variables~exporting-variables:~$  COLLEGE=PWN
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ PWN=COLLEGE
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ export PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{YDeMPLzeLXlLiOhxG9GQjpubYql.QXyYTN0wCO5kjNzEzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$
```
I simply wrote in terminal COLLEGE=PWN. Then, I wrote PWN=COLLEGE. Afterwards, I ran export PWN. Finally, I ran /challenge/run to get the flag.
### What I learned
By default, variables that we set in a shell session are local to that shell process. That is, other commands you run won't inherit them. If we want other shell sessions to be able to access that variable, we need to export the variable using the
export command.
### My References
Instructions in pwn.college website


### Task 5
This challenge asks to use the env command to print the FLAG variable.
### My Solve
Flag:pwn.college{ADrYQIJIQWEL8XWYj7rGp1U7LTr.QX4UTN0wCO5kjNzEzW}
```
hacker@variables~printing-exported-variables:~$ export FLAG
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=deb00de95de6dc7b4e6a0026713ef0cad785ccc72462139867ff59cc561ac499
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{ADrYQIJIQWEL8XWYj7rGp1U7LTr.QX4UTN0wCO5kjNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
hacker@variables~printing-exported-variables:~$
```
I simply exported the FLAG variable and ran env to get the flag,
### What I learned
The env command prints out every exported variable set in the shell.
### My References
Instructions in pwn.college website


### Task 6
This program asks to read the output of the /challenge/run command directly into a variable called PWN, which will contain the flag
### My Solve
Flag:pwn.college{0NVnGOh-a2iQkN9nFlSJ1BVPqK2.QX1cDN1wCO5kjNzEzW}
```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{0NVnGOh-a2iQkN9nFlSJ1BVPqK2.QX1cDN1wCO5kjNzEzW}
hacker@variables~storing-command-output:~$
```
I simply ran PWN=$(/challenge/run) and then echo $PWN to get the flag.
### What I learned
The process of storing output of a command directly into a variable using the format: variable=$(command) is called 
Command Substitution.
### My References
Instructions in pwn.college website


### Task 7
In this challenge, my job is to use read to set the PWN variable to the value COLLEGE.
### My Solve
Flag:pwn.college{Qw496BYVT77NljDZH6SaO54PEsJ.QX4cTN0wCO5kjNzEzW}
```
hacker@variables~reading-input:~$ read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Qw496BYVT77NljDZH6SaO54PEsJ.QX4cTN0wCO5kjNzEzW}
hacker@variables~reading-input:~$
```
I simply typed in terminal  read -p "INPUT: " PWN which asked for the input where I typed COLLEGE and got the flag.
### What I learned
The read builtin helps us read input into a variable. The -p argument helps to specify a prompt. The general format of this
is read -p "INPUT: " MY_VARIABLE.
### My References
Instructions in pwn.college website


### Task 8
The challenge wants us to redirect the input of  /challenge/read_me to variable PWN and read it without using cat command.
### My Solve
Flag:pwn.college{QgSr3k-GurnszPeWIipEAihTxhy.QXwIDO0wCO5kjNzEzW}
```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QgSr3k-GurnszPeWIipEAihTxhy.QXwIDO0wCO5kjNzEzW}
hacker@variables~reading-files:~$
```
I simply ran read PWN < /challenge/read_me to direct the standard input of read to the variable PWN and read it directly within this single command without cat command.
### What I learned
Simultaneously redirecting input of read command and printing it within the same single command.
### My References
Instructions in pwn.college website
































































