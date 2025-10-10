# Digesting Documentation
### Task 1
This challenge asks to invoke the flag running the /challenge/challenge command with a argument --giveflag.
### My Solve
Flag:pwn.college{oVLsDZlxgU2kZgrbuo6XCEezBY2.QX0ITO0wCO5kjNzEzW}
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{oVLsDZlxgU2kZgrbuo6XCEezBY2.QX0ITO0wCO5kjNzEzW}
hacker@man~learning-from-documentation:~$
```
Just running the /challenge/challenge command with the correct argument of --giveflag (mentioned in the challenge)
helps me obtain the flag.
### What I learned
Using a command with the right argument is necessary for it to work.
### References
Instructions in the pwn.college


### Task 2
This challenge asks to invoke the /challenge/challenge command with an argument of --printflag. The --printflag also has an argument of the file name which prints the flag.
### My Solve
Flag:pwn.college{0kMDWt1V7tjGn2Xhq4Q_fEfwG2M.QX1ITO0wCO5kjNzEzW}
```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{0kMDWt1V7tjGn2Xhq4Q_fEfwG2M.QX1ITO0wCO5kjNzEzW}
hacker@man~learning-complex-usage:~$
```
Same as Task 1, the only difference is there is an additional argument to an argument to obtain the flag. This 
signifies that some commands can have arguments to the arguments being passed onto them, i.e some commands are
analogous.
### What I learned
Nested arguments, and that some commands are analogous(can contain nested arguments).
### References
Instructions in the pwn.college


### Task 3
This challenge asks to read a document using the man command and understand from it how to obtain the flag in this challenge.
### My Solve
Flag: pwn.college{w1ucr2thpE0hfqQHJ-XkEGY3A2r.QX0EDO0wCO5kjNzEzW}
```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --wucrth 120
Correct usage! Your flag: pwn.college{w1ucr2thpE0hfqQHJ-XkEGY3A2r.QX0EDO0wCO5kjNzEzW}
hacker@man~reading-manuals:~$
```
I invoked the man command to read a document called challenge and by reading it, I understand that I have to invoke the command /challenge/challenge with the argument --wucrth which prints the flag if the argument is 120
Hence, I write /challenge/challenge --wucrth 120 in the terminal to obtain the flag.
### What I learned
Usage of the man command and that is used to display information about the command specified in its argument.
### References
Instructions in the pwn.college.


### Task 4
 This challenge asks to search for the argument in the challenge document which will give the flag.
### My Solve
Flag:pwn.college{UCk8J0mjC95VG3mNlz8tlOis-zt.QX1EDO0wCO5kjNzEzW}
```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --pbdafic
Initializing...
Correct usage! Your flag: pwn.college{UCk8J0mjC95VG3mNlz8tlOis-zt.QX1EDO0wCO5kjNzEzW}
hacker@man~searching-manuals:~$
```
I used the / command to search for the flag and used n for viewing the next element that matches with my search argument which I provided as flag.
I typed /flag and kept on typing n to go to the next search result until i found a command called --pbdafic which prints the flag. Finally, I ran /challenge/challenge --pbdafic to get the desired flag.
### What I learned
Utility of the search command / and using N and n to go to the previous and next search result respectively.
### References
Instructions in the pwn.college.


### Task 5
This challenge asks to search for the right manual by applying man man command and hence by eventually finding the right manual and following proper instructions,
we obtain the flag.
### My Solve 
Flag:pwn.college{w9USrI-KXW2a3Q6a8dxCBD6i34g.QX2EDO0wCO5kjNzEzW}
```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
wraadxigwk (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man wraadxigwk
hacker@man~searching-for-manuals:~$ /challenge/challenge  --wraadx 923
Correct usage! Your flag: pwn.college{w9USrI-KXW2a3Q6a8dxCBD6i34g.QX2EDO0wCO5kjNzEzW}
hacker@man~searching-for-manuals:~$
I ran the man man command to display a list of manuals. I ran the man -k challenge command(which I infered from the list of manuals) to print a manual called wraadxigwk.
I called the man command on the manual named wraadxigwk which instructed me to run the  --wraadx command with the argument of 923 to finally print the flag.
```
### What I learned
All of the manuals are present in a searchable database in this challenge.
We can use man command to manuals as argument as well to search for the required manual.
### References
Instructions in the pwn.college.


### Task 6
This challenge asks to read the documentation of a program using --help command.
### My Solve
Flag: pwn.college{kqiKhtZP7zEoM664tY47nUIZvpg.QX3IDO0wCO5kjNzEzW}
```
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge --p
The secret value is: 766
hacker@man~helpful-programs:~$ /challenge/challenge -g 766
Correct usage! Your flag: pwn.college{kqiKhtZP7zEoM664tY47nUIZvpg.QX3IDO0wCO5kjNzEzW}
hacker@man~helpful-programs:~$
```
I wrote /challenge/challenge --help in the terminal to get help and information with which I may proceed with the program. It showed me some commands within which -p and -g commands helped me to get the flag. I ran 
/challenge/challenge --p to print the secret value 766. Then, I ran /challenge/challenge -g 766 to get the flag.
### What I learned
The --help command can be used to get useful information about a program's documentation.
### References
Instructions in the pwn.college.


### Task 7
In this challenge, we are asked to invoke the help command on a built in named as challenge which will give us information on how to proceed with the challenge.
### My Solve
Flag:pwn.college{wAUbyhPlRm1loE0WeXudFjkLH-x.QX0ETO0wCO5kjNzEzW}
```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "wAUbyhPl".
hacker@man~help-for-builtins:~$ challenge --secret wAUbyhPl
Correct! Here is your flag!
pwn.college{wAUbyhPlRm1loE0WeXudFjkLH-x.QX0ETO0wCO5kjNzEzW}

hacker@man~help-for-builtins:~$
```
I wrote 'help challenge' in the terminal to get the necessary information and clue regarding the challenge. It gave me the information that i need to run the --secret command
with the secret value of "wAUbyhPl" to get the necessary flag.
### What I learned
Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs.
The challenge command in this challenge is a shell builtin rather than a program.
### References
Instructions in the pwn.college.













