# Shell Variables
### Task 1
This challenge asks to obtain the flag which has been stored in a variable called FLAG.
### My Solve
Flag:pwn.college{gD3HDJGRmNbhc4m4CyW7KoTe-vq.QX3UTN0wCO5kjNzEzW}

I simply ran echo $FLAG to print it as FLAG is a variable.
### What I learned
We can print out variables by echo command by prepending them with a $.
### My References
Instructions in pwn.college website.


### Task 2
This challenge asks to set the value of variable PWN to COLLEGE.
### My Solve
Flag:pwn.college{k_70KnrYX5SJuyOfC7-QL1yLDWE.QX5UTN0wCO5kjNzEzW}

I simply ran PWN=COLLEGE with no space in between to get the flag.
### What I learned
Assignment of variables.
### My References
Instructions in pwn.college website


### Task 3
This challenge asks to set the value of variable PWN to COLLEGE YEAH
### My Solve
Flag:pwn.college{c7OSkD9xsRhoAYIaViNQisYJLqE.QXwYTN0wCO5kjNzEzW}

I simply assign PWN="COLLEGE YEAH" as there cannot be any spaces in assignment of variables. As it is multi word value, I had to enclose the value in double quotation.
### What I learned
Assignment of variables of values separated by spaces.
### My References
Instructions in pwn.college website


### Task 4
This challenge asks to assign PWN to value COLLEGE and export it and assign COLLEGE to value PWN and not export it.
### My Solve
Flag:pwn.college{YDeMPLzeLXlLiOhxG9GQjpubYql.QXyYTN0wCO5kjNzEzW}

I simply wrote in terminal COLLEGE=PWN. Then, I wrote PWN=COLLEGE. Afterwards, I ran export PWN. Finally, I ran /challenge/run to get the flag,
### What I learned
Concept of exporting variables.
### My References
Instructions in pwn.college website


### Task 5
This challenge asks to use the env command to print the FLAG variable.
### My Solve
Flag:pwn.college{ADrYQIJIQWEL8XWYj7rGp1U7LTr.QX4UTN0wCO5kjNzEzW}

I simply exported the FLAG variable and ran env to get the flag,
### What I learned
Usage of env command.
### My References
Instructions in pwn.college website


### Task 6
This program asks to read the output of the /challenge/run command directly into a variable called PWN, which will contain the flag
### My Solve
Flag:pwn.college{0NVnGOh-a2iQkN9nFlSJ1BVPqK2.QX1cDN1wCO5kjNzEzW}

I simply ran PWN=$(/challenge/run) and then echo $PWN to get the flag.
### What I learned
Concept of storing outputs of commands in variables
### My References
Instructions in pwn.college website


### Task 7
In this challenge, my job is to use read to set the PWN variable to the value COLLEGE.
### My Solve
Flag:pwn.college{Qw496BYVT77NljDZH6SaO54PEsJ.QX4cTN0wCO5kjNzEzW}

I simply typed in terminal  read -p "INPUT: " PWN COLLEGE which asked for the input where I typed COLLEGE and got the flag.
### What I learned
Storing input of commands in variables.
### My References
Instructions in pwn.college website


### Task 8
The challenge wants us to redirect the input of  /challenge/read_me to variable PWN and read it without using cat command.
### My Solve
Flag:pwn.college{QgSr3k-GurnszPeWIipEAihTxhy.QXwIDO0wCO5kjNzEzW}

I simply ran read PWN < /challenge/read_me to direct the standard input of read to the variable PWN and read it directly within this single command without cat command.
### What I learned
Simultaneously redirecting input of read command and printing it within the same single command.
### My References
Instructions in pwn.college website
































































