# Practicing Piping
### Task 1
This challenge asks to redirect the output of printing the word PWN to a file named COLLEGE.
### My Solve
Flag:pwn.college{cPSRfzsVpx-U-ndP76IB37WiYda.QX0YTN0wCO5kjNzEzW}
I simply typed echo PWN > COLLEGE to redirect the output of the printing of the word PWN into the file named college.
### What I learned
We can use > command to redirect the output.
### References
Instructions in the pwn.college website.


### Task 2
This challenge asks to redirect the output of the /challenge/run command into a file named myflag.
### My Solve
Flag:pwn.college{UUx-HcS8wZeaL4Mrvy636NF60fH.QX1YTN0wCO5kjNzEzW}

I simple ran /challenge/run > myflag and used cat myflag to display the flag.
### What I learned
We can use > on any command.
### References
Instructions in the pwn.college website.


### Task 3
This challenge asks to redirect the output in append mode as the flag has been divided into two parts.
### My Solve
Flag:pwn.college{4pNEwXp7kVvOsHvXhHDdjrTaPyd.QX3ATO0wCO5kjNzEzW}

I ran /challenge/run > the-flag and ran /challenge/run >> the-flag to print the second part of the flag. Finally, I ran cat the-flag to get the flag.
### What I learned
We can use >> to redirect the output of a command in append mode.
### References
Instructions in the pwn.college website.


### Task 4
This challenge asks to redirect the output as well errors of the /challenge/run command in the terminal simultaneously.
### My Solve
Flag: pwn.college{EK9yjquH4t1hsUgI9aA5kwm1ds4.QX3YTN0wCO5kjNzEzW}

I ran the command /challenge/run > myflag 2> instructions to redirect the output in a file named myflag and errors in a file named instructions. i used cat myflag
to finally to get the flag.
### What I learned
Inputs and errors can also be redirected by specifing 0> and 2> respectively (1> is default)
### References
Instructions in the pwn.college website.


### Task 5
This challenge asks to redirect the PWN file to standard input
### My Solve
Flag:pwn.college{EX7RT_Ywmd41QoErYjrqED131CN.QXwcTN0wCO5kjNzEzW}

Firstly, I ran echo COLLEGE > PWN to redirect the output of printing COLLEGE to the PWN file. Then, I ran /challenge/run < PWN to redirect the standard input
of PWN and read the value COLLEGE out of it which contained the flag.
### What I learned
Redirecting input.
### References
Instructions in the pwn.college website.


### Task 6
This challenge asks to grep the stored result of the output of /challenge/run stored in a text file named data in the path : /tmp/data.txt
### My Solve
Flag:pwn.college{8E1-bQf2FgrjZGjDhdO34Vb2lwE.QX4EDO0wCO5kjNzEzW}

I redirected the output of /challenge/run to /tmp/data.txt and ran grep pwn.college /tmp/data.txt to get the flag.
### What I learned
Grepping the stored result for the flag.
### References
Instructions in the pwn.college website.


### Task 7
This challenge asks to do the same as task 6 without storing the result in a file and  rather using | pipe operator.
### My Solve
Flag:pwn.college{EJdWhEKqbhtfw84mkqsKsa3UzRE.QX5EDO0wCO5kjNzEzW}

I ran /challenge/run | grep pwn.college to get the flag. Here, the pipe operator takes the output of the command of the left and feeds it into
the command to the right side as an input. This avoids storing the result in a file.
### What I learned
Usage of the pipe operator
### References
Instructions in the pwn.college website.


### Task 8
This challenge asks to redirect the errors(containing flag in one of them) to the standard output so that a pipe operator can be used as the previous task
as the | operator redirects only standard output to another program, and there is no 2| form of the operator
### My Solve
Flag:pwn.college{suTmZZFs0XGs8Qu4JIH1N0mJMqM.QX1ATO0wCO5kjNzEzW}

I ran /challenge/run 2>&1 | grep pwn.college to redirect the errors to the standard output of the /challenge/run command which makes it valid for the
pipe operator to work as it is intended.
### What I learned
Usage of the >& operator which redirects a file descriptor to another file descriptor.
### References
Instructions in the pwn.college website.


### Task 9
This challenge asks to filter out the flag using grep -v command from the stdout of /challenge/run
### My Solve
Flag:pwn.college{Evuh_ldPPf79xa6_SP1CUIYzQ3W.0FOxEzNxwCO5kjNzEzW}

I ran /challenge/run | grep -v DECOY to filter out lines which do not have DECOY in them. The one real flag does not have DECOY written in it,
so I obtain the flag.
### What I learned
Usage of the grep -v command.
### References
Instructions in the pwn.college website.


### Task 10
This challenge asks to pipe /challenge/pwn into /challenge/college, for which we need to read the intercepted data.
### My Solve
Flag:pwn.college{gfqOwtEA09ucSadmM3FNZkkI3KQ.QXxITO0wCO5kjNzEzW}

I ran /challenge/pwn | tee intercepted_output | /challenge/college initially to store output of /challenge/pwn in intercepted_output and pipe the same
to /challenge/college. I displayed the intercepted_output which gave the secret value of gfqOwtEA.
Finally, I ran /challenge/pwn --secret gfqOwtEA | tee intercepted_output | /challenge/college to get the flag.
### What I learned
Usage of the tee command.
### References
Instructions in the pwn.college website.


### Task 11
This challenge asks to use process substitution and the diff command to find the flag.
### My Solve
Flag: pwn.college{coQeKt0HQp_8fefHZi1pT97Eo_C.0lNwMDOxwCO5kjNzEzW}

I ran diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag) to compare the two outputs of the commands which result in the difference
of the print_decoys_and_flag containing the flag. After running the command, I obtain the flag.
### What I learned
Concept of process substitution.
### References
Instructions in the pwn.college website.


### Task 12
This challenge asks to duplicate the output of two programs /challenge/the and /challenge/planet.
### My Solve
Flag:pwn.college{UAX0JDKOkstn0xtiUMveJLC1TnP.QXwgDN1wCO5kjNzEzW}

I simply ran /challenge/hack | tee >(/challenge/the) >(/challenge/planet) to copy the output of /challenge/hack into two programs /challenge/the and /challenge/planet
and I obtained the flag.
### What I learned
More clarity on the concept of process substitution.
### References
Instructions in the pwn.college website.


### Task 13
This challenge asks to redirect the errors of /challenge/hack program to /challenge/the and output to /challenge/planet.
### My Solve
Flag:pwn.college{wooM7JyV_nTe-W4iz-nZxBJ8yQK.QXxQDM2wCO5kjNzEzW}

I ran /challenge/hack 2> >(/challenge/the) | (/challenge/planet) to redirect the errors into /challenge/the and the output to /challenge/planet.
### What I learned
Problem Solving.
### References
Instructions in the pwn.college website.


### Task 14
This challenge asks to create a fifo file in the path of /tmp/flag_fifo and redirect the output of /challenge/run to it.
### My Solve
Flag:pwn.college{U4LziLJdI3NNIRixxiV7Um282ZL.01MzMDOxwCO5kjNzEzW}

I ran the command mkfifo /tmp/flag_fifo to make a fifo file in the path /tmp/flag_fifo and ran /challenge/run > /tmp/flag_fifo &
cat /tmp/flag_fifo to simultaneously start writing to and reading of the file as FIFOs block until both reader and writer connect. The
/challenge/run > /tmp/flag_fifo starts writing the stdout of /challenge/run to the fifo file and cat /tmp/flag_fifo starts reading it.
### What I learned
Concept of FIFO(First In First Out)
### References
Instructions in the pwn.college website.







































































































