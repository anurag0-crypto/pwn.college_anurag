
# Comprehending Commands
### Task 1
This challenge asks to read the flag file using cat and hence obtain the flag.
### My Solve 
Flag:pwn.college{A9SPP_Rlaa-LSrjJWtV3tWbxShD.QXxcTN0wCO5kjNzEzW}
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{A9SPP_Rlaa-LSrjJWtV3tWbxShD.QXxcTN0wCO5kjNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$
```
I used the cat command to display the contents of the flag file and hence obtain the flag.
### What I learned
We can use cat command to read a file by specifying the file name as argument to the cat command.
### References
Instructions in pwn.college.


### Task 2
This challenge asks to read the flag from its absolute path.
### My Solve
Flag:pwn.college{wX17exKyxwFBmtiFJLNsmgxhFkS.QX5ETO0wCO5kjNzEzW}
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{wX17exKyxwFBmtiFJLNsmgxhFkS.QX5ETO0wCO5kjNzEzW}
hacker@commands~catting-absolute-paths:~$
```
I used the cat command to read flag from its absolute directory i.e  cat /flag to get the flag.
### What I learned
We can also read from a absolute path using cat command by specifying the path to the argument of cat command.
### References
Instructions in pwn.college.


### Task 3
This challenge asks to retrieve the flag from a different directory than home without using the cd command.
### My Solve
Flag:pwn.college{c6ajjHzXxgMc8nvc9OMtvgdMBFA.QXwITO0wCO5kjNzEzW}
```
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/lib/aspell/flag. Go cat it out **without** cding into that
directory!
hacker@commands~more-catting-practice:~$ cat /usr/lib/aspell/flag
pwn.college{c6ajjHzXxgMc8nvc9OMtvgdMBFA.QXwITO0wCO5kjNzEzW}
hacker@commands~more-catting-practice:~$
```
Directly invoking the cat command to the path given to the patricular directory named /usr/lib/aspell/flag
helped me fetch the flag.
### What I learned
We can directly invoke the command on a path without needing to change the working directory using cd.
### References
Instructions in pwn.college.


### Task 4
This challenge asks to search for the flag in a given file containing lines of text using the grep command.
### My Solve
Flag:pwn.college{QHeiQhlB-n2PClDWbQqzi_viMYM.QX3EDO0wCO5kjNzEzW}
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{QHeiQhlB-n2PClDWbQqzi_viMYM.QX3EDO0wCO5kjNzEzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$
```
I used the grep command with the argument of "pwn.college" to search for the flag within the file as the flag
always starts with "pwn.college".
### What I learned
Learnt the usage of the grep command and how it can be used to search for a string within lines of text
of a file.
### References
Instructions in pwn.college.


### Task 5
This challenge provides two flags: one containing 100 fake flags and one containing 100 fake flags with one real one. I am asked to find the flag using the diff command.
### My Solve
Flag: pwn.college{4cpgubrgZHqUAVVgQoC4_mbqE0n.01MwMDOxwCO5kjNzEzW}
```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
32a33
> pwn.college{4cpgubrgZHqUAVVgQoC4_mbqE0n.01MwMDOxwCO5kjNzEzW}
hacker@commands~comparing-files:~$
```
I used the diff command with the two files as arguments. As 100 fake flags of the two files are same, the diff command prints the line containing the real flag and hence the challenge is completed.
The 32a33 signifies that there is an additional line after 32 lines in second file which
contains the flag when compared to 32 lines of decoy in first file.
### What I learned
Usage of the diff command and how it can be used to compare the content of two files.
### References
Instructions in pwn.college.


### Task 6
This challenge asks to list files present in the /challenge directory to find the flag using the ls command.
### My Solve
Flag: pwn.college{wbZhpPEV0fb1ZwrBaxI6-FW9khP.QX4IDO0wCO5kjNzEzW}
```
hacker@commands~listing-files:~$ ls /challenge
14842-renamed-run-31686  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/run 14842-renamed-run-31686
bash: /challenge/run: No such file or directory
hacker@commands~listing-files:~$ /challenge/14842-renamed-run-31686
Yahaha, you found me! Here is your flag:
pwn.college{wbZhpPEV0fb1ZwrBaxI6-FW9khP.QX4IDO0wCO5kjNzEzW}
hacker@commands~listing-files:~$
```
I used the ls command on /challenge directory which I passed as an argument to the command, which listed out all non hidden files present in /challenge. I ran a file called 14842-renamed-run-31686 to get the flag.
### What I learned
Usage of the ls command and how it can be used to list files in all the directories provided to it as arguments.
### References
Instructions in pwn.college.


### Task 7
This challenge asks to create two flags in /tmp directory named pwn and college and run /challenge/run to get the flag.
### My Solve
Flag: pwn.college{8SORjdaYWese_s3JsugUXBb1rb_.QXwMDO0wCO5kjNzEzW}

I used cd command to change the directory to /tmp and used the touch command to create two flags pwn and college. I finally ran /challenge/run to get the flag.
### What I learned
Usage of the touch command.
### References
Instructions in pwn.college.


### Task 8
This challenge asks me to remove the delete_me file from my home directory.
### My Solve
Flag: pwn.college{AVUF9BHqcBbSOqLcGkPJ2jANMYy.QX2kDM1wCO5kjNzEzW}

I used the ls command to view the delete_me flag which i removed using the rm command and ran /challenge/check command to obtain the flag.
### What I learned
Usage of the rm command.
### References
Instructions in pwn.college.


### Task 9
This challenge asks to move /flag file to /tmp/hack-the-planet.
### My Solve
Flag: pwn.college{AVUF9BHqcBbSOqLcGkPJ2jANMYy.QX2kDM1wCO5kjNzEzW}

I used the mv command with two arguments /flag and /tmp/hack-the-planet to move flag file directly.
### What I learned
Usage of the mv command.
### References
Instructions in pwn.college.


### Task 10
This challenge asks to find the flag present in the hidden directory.
### My Solve
Flag: pwn.college{Imk2bIMjj5K2NbouKnrrkDbEqAa.QXwUDO0wCO5kjNzEzW}

I used cd / to change the directory to / and ran the ls -a command to list the hidden files present as well in the directory.(-a is a special argument to the ls command)
I found a . prepended flag file which I ran using the cat command to get the necessary flag.
### What I learned
Usage of the ls -a command.
### References
Instructions in pwn.college.


### Task 11
This challenge asks to find the flag by repeated procedure of looking about clues by changing the directory using cd and listing files in that directory to look for clues
and head to the next directory and so on...
### My Solve
Flag:  pwn.college{U_TVpwFIZlak0VpsZtdSTSZeGja.QX5IDO0wCO5kjNzEzW}

After looking around clues in different directories by ls -la(to list out hidden files and directories as well) I found the flag eventually by using cat to display the clues
and finally which led to me finding the flag.
### What I learned
Problem Solving
### References
Instructions in pwn.college.


### Task 12
This challenge asks to make a new directory named pwn in /tmp directory and create a file named college in it.
### My Solve
Flag:pwn.college{0sqCJzuCcSW5FEwPTLvAsSg3tNs.QXxMDO0wCO5kjNzEzW}

I use cd to change the directory to /tmp and use mkdir command to make a new directory named pwn in /tmp. Then, I use the touch command to create a file named college in it.
Finally, I run /challenge/run to get the flag.
### What I learned
Usage of the mkdir command
### References
Instructions in pwn.college.


### Task 13
This challenge asks to find the flag in the hidden directory using the find command.
### My Solve
Flag:pwn.college{0sqCJzuCcSW5FEwPTLvAsSg3tNs.QXxMDO0wCO5kjNzEzW}

Using the find command will list out some accessible files containing the name flag in them, out of which each file must be displayed with cat until the correct flag is 
found.
### What I learned
Usage of the find command
### References
Instructions in pwn.college.


### Task 14
The challenge states that there is a program called /challenge/catflag that is hardcoded to read /home/hacker/not-the-flag instead of /flag. We have to use symlink
to fool the operating system to read /flag instead.
### My Solve
Flag:pwn.college{s-wYMv687yB6chQoKFUyjhlEg9E.QX5ETN1wCO5kjNzEzW}

I used rm command to remove the /home/hacker/not-the-flag and used a symlink to open the /flag instead when referring to the /home/hacker/not-the-flag using the ln -s 
command. I finally ran the /challenge/catflag command to get the flag.
### What I learned
Concept of symbolic links.
### References
Instructions in pwn.college.
