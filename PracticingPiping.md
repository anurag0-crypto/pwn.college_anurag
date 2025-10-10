# Practicing Piping
### Task 1
This challenge asks to redirect the output of printing the word PWN to a file named COLLEGE.
### My Solve
Flag:pwn.college{cPSRfzsVpx-U-ndP76IB37WiYda.QX0YTN0wCO5kjNzEzW}
```
You have created the COLLEGE file and wrote the right value to it, but it
doesn't look like you did it via input redirection.
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{cPSRfzsVpx-U-ndP76IB37WiYda.QX0YTN0wCO5kjNzEzW}
hacker@piping~redirecting-output:~$
```
I simply typed echo PWN > COLLEGE to redirect the output of the printing of the word PWN into the file named college.
### What I learned
We can use > command to redirect the output.
### References
Instructions in the pwn.college website.


### Task 2
This challenge asks to redirect the output of the /challenge/run command into a file named myflag.
### My Solve
Flag:pwn.college{UUx-HcS8wZeaL4Mrvy636NF60fH.QX1YTN0wCO5kjNzEzW}
```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{UUx-HcS8wZeaL4Mrvy636NF60fH.QX1YTN0wCO5kjNzEzW}

hacker@piping~redirecting-more-output:~$
```
I simple ran /challenge/run > myflag to redirect the output of /challenge/run to myflag and 
used cat myflag to display the flag.
### What I learned
Aside from redirecting the output of echo, we can redirect the output of any command.
### References
Instructions in the pwn.college website.


### Task 3
This challenge asks to redirect the output in append mode as the flag has been divided into two parts.
### My Solve
Flag:pwn.college{4pNEwXp7kVvOsHvXhHDdjrTaPyd.QX3ATO0wCO5kjNzEzW}
```
hacker@piping~appending-output:~$ /challenge/run > the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ /challenge/run >> the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat the-flag
 |
\|/ This is the first half:
 v
pwn.college{4pNEwXp7kVvOsHvXhHDdjrTaPyd.QX3ATO0wCO5kjNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
hacker@piping~appending-output:~$
```
I ran /challenge/run > the-flag to print the first part of the flag and ran /challenge/run >> the-flag to print the second part of the flag. Specifying >> rather than > appends the second part of the flag rather than overwrite it over the first the part of the flag. Finally, I ran cat the-flag to get the flag.
### What I learned
A common use-case of output redirection is to save off some command results for later analysis. Often times, we may want to do this in aggregate: run a bunch of commands, save their output, and grep through it later. In this case,we might want all that output to keep appending to the same file, but > will create a new output file every time, deleting the old contents.
Instead of >, we can use >> to redirect the output of a command in append mode.
### References
Instructions in the pwn.college website.


### Task 4
This challenge asks to redirect the output as well errors of the /challenge/run command in the terminal simultaneously.
### My Solve
Flag: pwn.college{EK9yjquH4t1hsUgI9aA5kwm1ds4.QX3YTN0wCO5kjNzEzW}
```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{EK9yjquH4t1hsUgI9aA5kwm1ds4.QX3YTN0wCO5kjNzEzW}

hacker@piping~redirecting-errors:~$
```
I ran the command /challenge/run > myflag 2> instructions to redirect the output in a file named myflag and errors in a file named instructions.
I used cat myflag to finally to get the flag.
### What I learned
Just like standard output, we can also redirect the error channel of commands.
A File Descriptor (FD) is a number that describes a communication channel in Linux.
There are three types of file descriptors:
FD 0: Standard Input
FD 1: Standard Output
FD 2: Standard Error
Inputs and errors can also be redirected by specifing 0> and 2> respectively (1> is default)
### References
Instructions in the pwn.college website.


### Task 5
This challenge asks to redirect the PWN file to standard input
### My Solve
Flag:pwn.college{EX7RT_Ywmd41QoErYjrqED131CN.QXwcTN0wCO5kjNzEzW}
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{EX7RT_Ywmd41QoErYjrqED131CN.QXwcTN0wCO5kjNzEzW}
hacker@piping~redirecting-input:~$
```
Firstly, I ran echo COLLEGE > PWN to redirect the output of printing COLLEGE to the PWN file. Then, I ran /challenge/run < PWN to redirect the standard input
of PWN and read the value COLLEGE out of it which contained the flag.
### What I learned
We can redirect the input of any command using <
### References
Instructions in the pwn.college website.


### Task 6
This challenge asks to grep the stored result of the output of /challenge/run stored in a text file named data in the path : /tmp/data.txt
### My Solve
Flag:pwn.college{8E1-bQf2FgrjZGjDhdO34Vb2lwE.QX4EDO0wCO5kjNzEzW}
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{8E1-bQf2FgrjZGjDhdO34Vb2lwE.QX4EDO0wCO5kjNzEzW}
hacker@piping~grepping-stored-results:~$
```
I redirected the output of /challenge/run to /tmp/data.txt and ran grep pwn.college /tmp/data.txt to get the flag.
### What I learned
Grepping the stored result for the flag.
### References
Instructions in the pwn.college website.


### Task 7
This challenge asks to do the same as task 6 without storing the result in a file and  rather using | pipe operator.
### My Solve
Flag:pwn.college{EJdWhEKqbhtfw84mkqsKsa3UzRE.QX5EDO0wCO5kjNzEzW}
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{EJdWhEKqbhtfw84mkqsKsa3UzRE.QX5EDO0wCO5kjNzEzW}
hacker@piping~grepping-live-output:~$
```
I ran /challenge/run | grep pwn.college to get the flag. Here, the pipe operator takes the output of the command of the left and feeds it into
the command to the right side as an input. This avoids storing the result in a file.
### What I learned
It turns out that we can cut out the middleman and avoid the need to store results to a file, like I did in the last level. We can do this by using the | (pipe) operator. Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe.
### References
Instructions in the pwn.college website.


### Task 8
This challenge asks to redirect the errors(containing flag in one of them) to the standard output so that a pipe operator can be used as the previous task
as the | operator redirects only standard output to another program, and there is no 2| form of the operator
### My Solve
Flag:pwn.college{suTmZZFs0XGs8Qu4JIH1N0mJMqM.QX1ATO0wCO5kjNzEzW}
```
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{suTmZZFs0XGs8Qu4JIH1N0mJMqM.QX1ATO0wCO5kjNzEzW}
hacker@piping~grepping-errors:~$
```
I ran /challenge/run 2>&1 | grep pwn.college to redirect the errors to the standard output of the /challenge/run command which makes it valid for the
pipe operator to work as it is intended.
### What I learned
The shell has a >& operator, which redirects a file descriptor to another file descriptor. This means that we can have a two-step process to grep through errors: first, we redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal (|)!
The >& operator redirects a file descriptor to another file descriptor.
### References
Instructions in the pwn.college website.


### Task 9
This challenge asks to filter out the flag using grep -v command from the stdout of /challenge/run
### My Solve
Flag:pwn.college{Evuh_ldPPf79xa6_SP1CUIYzQ3W.0FOxEzNxwCO5kjNzEzW}
```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{Evuh_ldPPf79xa6_SP1CUIYzQ3W.0FOxEzNxwCO5kjNzEzW}
hacker@piping~filtering-with-grep-v:~$
```
I ran /challenge/run | grep -v DECOY to filter out lines which do not have DECOY in them. The one real flag does not have DECOY written in it,so I obtained the flag.
### What I learned
The grep command has a very useful option: -v (invert match). While normal grep shows lines that MATCH a pattern, grep -v shows lines that do NOT match a pattern.
### References
Instructions in the pwn.college website.


### Task 10
This challenge asks to pipe /challenge/pwn into /challenge/college, for which we need to read the intercepted data.
### My Solve
Flag:pwn.college{gfqOwtEA09ucSadmM3FNZkkI3KQ.QXxITO0wCO5kjNzEzW}
```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{Evuh_ldPPf79xa6_SP1CUIYzQ3W.0FOxEzNxwCO5kjNzEzW}
hacker@piping~filtering-with-grep-v:~$
Connected!
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee intercepted_output | /challenge/college
Processing...
WARNING: you are overwriting file intercepted_output with tee's output...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat intercepted_output
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "gfqOwtEA"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret gfqOwtEA | tee intercepted_output | /challenge/college
Processing...
WARNING: you are overwriting file intercepted_output with tee's output...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{gfqOwtEA09ucSadmM3FNZkkI3KQ.QXxITO0wCO5kjNzEzW}
hacker@piping~duplicating-piped-data-with-tee:~$
```
I ran /challenge/pwn | tee intercepted_output | /challenge/college initially to store output of /challenge/pwn in intercepted_output and pipe the same
to /challenge/college. I displayed the intercepted_output which gave the secret value of gfqOwtEA.
Finally, I ran /challenge/pwn --secret gfqOwtEA | tee intercepted_output | /challenge/college to get the flag.
### What I learned
When we pipe data from one command to another, we of course no longer see it on our screen. This is not always desired: for example, we may want to see the data as it flows through between our commands to debug unintended outcomes.
Fortunately,for this, there is a tee command, named after a "T-splitter" from plumbing pipes,which  duplicates data flowing through  pipes to any number of files provided on the command line.
### References
Instructions in the pwn.college website.


### Task 11
This challenge asks to use process substitution and the diff command to find the flag.
### My Solve
Flag: pwn.college{coQeKt0HQp_8fefHZi1pT97Eo_C.0lNwMDOxwCO5kjNzEzW}
```
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
67a68
> pwn.college{coQeKt0HQp_8fefHZi1pT97Eo_C.0lNwMDOxwCO5kjNzEzW}
hacker@piping~process-substitution-for-input:~$
```
I ran diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag) to compare the two outputs of the commands which result in the difference
of the print_decoys_and_flag containing the flag. After running the command, I obtain the flag.
### What I learned
Interestingly, we can hook input and output of programs to arguments of commands. This is done using Process Substitution. For reading from a command (input process substitution), we can use <(command). When we  write <(command), bash will run the command and hook up its output to a temporary file that it will create. This isn't a real file, of course, it's what's called a named pipe.
### References
Instructions in the pwn.college website.


### Task 12
This challenge asks to duplicate the output of two programs /challenge/the and /challenge/planet.
### My Solve
Flag:pwn.college{UAX0JDKOkstn0xtiUMveJLC1TnP.QXwgDN1wCO5kjNzEzW}
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and
/challenge/planet. Don't try to copy-paste it; it changes too fast.
727530202428710479
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{UAX0JDKOkstn0xtiUMveJLC1TnP.QXwgDN1wCO5kjNzEzW}
hacker@piping~writing-to-multiple-programs:~$
```
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
```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | (/challenge/planet)
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:
pwn.college{wooM7JyV_nTe-W4iz-nZxBJ8yQK.QXxQDM2wCO5kjNzEzW}
hacker@piping~split-piping-stderr-and-stdout:~$
```
I ran /challenge/hack 2> >(/challenge/the) | (/challenge/planet) to redirect the errors into /challenge/the and the output to /challenge/planet.
### What I learned
Problem Solving.
### References
Instructions in the pwn.college website.


### Task 14
This challenge asks to create a fifo file in the path of /tmp/flag_fifo and redirect the output of /challenge/run to it.
### My Solve
Flag:pwn.college{U4LziLJdI3NNIRixxiV7Um282ZL.01MzMDOxwCO5kjNzEzW}
```
hacker@piping~named-pipes:~$ mkfifo  /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo & cat /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!
[1] 171
You've correctly redirected /challenge/run's stdout to a FIFO at
/tmp/flag_fifo! Here is your flag:
pwn.college{U4LziLJdI3NNIRixxiV7Um282ZL.01MzMDOxwCO5kjNzEzW}
[1]+  Done                    /challenge/run > /tmp/flag_fifo
hacker@piping~named-pipes:~$
```
I ran the command mkfifo /tmp/flag_fifo to make a fifo file in the path /tmp/flag_fifo and ran /challenge/run > /tmp/flag_fifo &
cat /tmp/flag_fifo to simultaneously start writing to and reading of the file as FIFOs block until both reader and writer connect. The
/challenge/run > /tmp/flag_fifo starts writing the stdout of /challenge/run to the fifo file and cat /tmp/flag_fifo starts reading it.
### What I learned
We can also create our own persistent named pipes that stick around on the filesystem.These are called FIFOs, which stands for First (byte) In, First (byte) Out. We create a FIFO using the mkfifo command.Unlike the automatic named pipes from process substitution:

We can control where FIFOs are created
They persist until we delete them
Any process can write to them by path (e.g., echo hi > my_pipe)
We can see them with ls and examine them like files
One problem with FIFOs is that they'll "block" any operations on them until both the read side of the pipe and the write side of the pipe are ready.
Properties of FIFO's:

No disk storage: FIFOs pass data directly between processes in memory - nothing is saved to disk
Ephemeral data: Once data is read from a FIFO, it's gone (unlike files where data persists)
Automatic synchronization: Writers block until the readers are ready, and vice-versa. This is actually useful! It provides automatic synchronization.With files, we need to make sure to execute the writer before the reader.
Complex data flows: FIFOs are useful for facilitating complex data flows, merging and splitting data in flexible ways, and so on. For example, FIFOs support multiple readers and writers.
### References
Instructions in the pwn.college website.







































































































