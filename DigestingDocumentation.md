# Digesting Documentation
### Task 1
This challenge asks to invoke the flag running the /challenge/challenge command with a argument --giveflag.
### My Solve
Flag:pwn.college{oVLsDZlxgU2kZgrbuo6XCEezBY2.QX0ITO0wCO5kjNzEzW}

Just running the /challenge/challenge command with the argument of --giveflag helps me obtain the flag.
### What I learned
Familiarising myself with the command line.
### References
Instructions in the pwn.college


### Task 2
This challenge asks to invoke the /challenge/challenge command with an argument of --printflag. The --printflag also has an argument of the file name which prints the flag.
### My Solve
Flag:pwn.college{0kMDWt1V7tjGn2Xhq4Q_fEfwG2M.QX1ITO0wCO5kjNzEzW}

Same as Task 1, the only difference is there is an additional argument to an argument to obtain the flag.
### What I learned
Nested arguments
### References
Instructions in the pwn.college


### Task 3
This challenge asks to read a document using the man command and understand from it how to obtain the flag in this challenge.
### My Solve
Flag: pwn.college{w1ucr2thpE0hfqQHJ-XkEGY3A2r.QX0EDO0wCO5kjNzEzW}

I invoke the man command to read a document called challenge and by reading it, I understand that I have to invoke the command  --wucrth which prints the flag
if the argument is 120. Hence, I write /challenge/challenge --wucrth 120 in the terminal to obtain the flag.
### What I learned
Usage of the man command
### References
Instructions in the pwn.college.


### Task 4
 This challenge asks to search for the argument in the challenge document which will give the flag.
 ### My Solve
 Flag:pwn.college{UCk8J0mjC95VG3mNlz8tlOis-zt.QX1EDO0wCO5kjNzEzW}

 I used the / command to search for the flag and used n for viewing the next element that matches with my search argument which I provided
 as flag. I typed /flag and kept on typing n to go to the next search result until i found a command called --pbdafic which prints the flag. Finally,
 I ran /challenge/challenge --pbdafic to get the desired flag.
 ### What I learned
 Utility of the search command / and using N and n to go to the previous and next search result respectively.
 ### References
Instructions in the pwn.college.


### Task 5
This challenge asks to search for the right manual by applying man man command and hence by eventually finding the right manual and following proper instructions,
we obtain the flag.
### My Solve 
Flag:pwn.college{w9USrI-KXW2a3Q6a8dxCBD6i34g.QX2EDO0wCO5kjNzEzW}

I ran the man man command to display a list of manuals. I ran the man -k challenge command(which I infered from the list of manuals) to print a manual called wraadxigwk.
I called the man command on the manual named wraadxigwk which instructed me to run the  --wraadx command with the argument of 923 to finally print the flag.
### What I learned
We can use man command to manuals as well to search for the required manual.
### References
Instructions in the pwn.college.


### Task 6
This challenge asks to read the documentation of a program using --help command.
### My Solve
Flag: pwn.college{kqiKhtZP7zEoM664tY47nUIZvpg.QX3IDO0wCO5kjNzEzW}

I wrote /challenge/challenge --help in the terminal to get help and information with which I may proceed with the program. It showed me two commands -p and -g. I ran 
/challenge/challenge --p to print the secret value 766. Then, I ran /challenge/challenge -g 766 to get the flag.
### What I learned
Usage of the --help command.
### References
Instructions in the pwn.college.


### Task 7
In this challenge, we are asked to invoke the help command on a built in named as challenge which will give us information on how to proceed with the challenge.
### My Solve
Flag:pwn.college{wAUbyhPlRm1loE0WeXudFjkLH-x.QX0ETO0wCO5kjNzEzW}

I wrote 'help challenge' in the terminal to get the necessary information and clue regarding the challenge. It gave me the information that i need to run the --secret command
with the secret value of "wAUbyhPl" to get the necessary flag.
### What I learned
Concept of built-ins.
### References
Instructions in the pwn.college.













