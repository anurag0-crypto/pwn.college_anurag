# Chaining Commands
### Task 1
This challenge asks to chain two commands /challenge/pwn and /challenge/college by separating them by a semicolon.
### My Solve
Flag:pwn.college{QiqJSLh5phVN1xlAZDzt--4tMUX.QX1UDO0wCO5kjNzEzW}
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{QiqJSLh5phVN1xlAZDzt--4tMUX.QX1UDO0wCO5kjNzEzW}
hacker@chaining~chaining-with-semicolons:~$
```
I simply typed /challenge/pwn; /challenge/college to chain and ran two commands simultaneously.
### What I learned
The easiest way to chain commands is ;. In most contexts, ; separates commands in a similar way to how Enter separates lines.
Basically, when you hit Enter, your shell executes your typed command and, after that command terminates, gives you the prompt to input another command. 
The semicolon is analogous, just without the prompt and with you entering both commands before anything is executed.
### References
Instructions in pwn.college website.


### Task 2
This challenge asks to chain commands with the && operator which only succeeds in chaining commands if the first command successfully runs.
### My Solve
Flag:pwn.college{YkQHfFA4i_jOi8iiTWCEjwPKLmw.0lM0MDOxwCO5kjNzEzW}
```
hacker@chaining~building-on-success:~$ /challenge/first-success
hacker@chaining~building-on-success:~$ /challenge/second
Error: /challenge/first-success must be successfully chained with
/challenge/second using &&
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{YkQHfFA4i_jOi8iiTWCEjwPKLmw.0lM0MDOxwCO5kjNzEzW}
hacker@chaining~building-on-success:~$
```
I chained /challenge/first-success and /challenge/second by the && operator and ran it to get the flag.
### What I learned
The && operator allows us to run a second command only if the first command succeeds (in Linux convention, this means it exited with code 0). This is called the "AND" operator 
because both conditions must be true: the first command must succeed AND then the second command will run.
That's super useful for complex commandline workflows where certain actions depend on the success of other actions.
### References
Instructions in pwn.college website


### Task 3
This challenge asks to chain two commands by the || operator which chains two commands in such a way that the second command only runs if the first one fails.
### My Solve
Flag: pwn.college{YDHfcSWfwd0NdDOHwm_4sLRkUhU.01M0MDOxwCO5kjNzEzW}
```
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{YDHfcSWfwd0NdDOHwm_4sLRkUhU.01M0MDOxwCO5kjNzEzW}
hacker@chaining~handling-failure:~$
```
The first command /challenge/first-failure is bound to fail so I chained it with /challenge/second so that the second command successfully runs and the 
flag is obtained.
### What I learned
The || operator allows us to run a second command only if the first command fails (exits with a non-zero code).
This is called the "OR" operator because either the first command succeeds OR the second command will run.
This is why the || operator is super useful for providing fallback commands or error handling.
### References
Instructions in the pwn.college website.


### Task 4
This challenge asks to run /challenge/pwn and /challenge/college in a shell script called x.sh and run it with the bash command.
### My Solve
Flag:pwn.college{kiugyBvEULGZ-RXULDX6tgdAnjI.QXxcDO0wCO5kjNzEzW}
```
hacker@chaining~your-first-shell-script:~$ echo /challenge/pwn > x.sh
hacker@chaining~your-first-shell-script:~$ echo /challenge/college >> x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{kiugyBvEULGZ-RXULDX6tgdAnjI.QXxcDO0wCO5kjNzEzW}
hacker@chaining~your-first-shell-script:~$
```
I redirected the output of echo /challenge/pwn and /challenge/college in a shell script called x.sh and ran it with the bash command which read sthe commands
from a file rather than directly taking and running it from the user,
### What I learned
As we combine more and more commands to achieve complex effects, the length of the combined prompt quickly gets really annoying to deal with. 
When this happens, we can put these commands in a file, called a shell script, and run them by executing the file
And then we can execute by passing it as an argument to a new instance of our shell (bash)! When a shell is invoked like this, 
rather than taking commands from the user, it reads commands from the file.
### References
Instructions in the pwn.college website


### Task 5
This challenge is similar to the previous one except that in this challenge we have to pipe the output of the bash command to /challenge/solve to get the flag.
### My Solve
Flag:pwn.college{cHgAxjcyuHL_8eu5lfu18H6f2Ni.QX4ETO0wCO5kjNzEzW}
```
hacker@chaining~redirecting-script-output:~$ echo /challenge/pwn > x.sh
hacker@chaining~redirecting-script-output:~$ echo /challenge/college >> x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{cHgAxjcyuHL_8eu5lfu18H6f2Ni.QX4ETO0wCO5kjNzEzW}
hacker@chaining~redirecting-script-output:~$
```
 I performed similar operations like the previous task, except that I redirected the output of the bash command to /challenge/solve to get the flag.
 ### What I learned
 Nothing new since the previous task.
 ### References
 Instructions in pwn.college website


### Task 6
This challenge asks to make a shellscript which will invoke /challenge/solve, and then to make it executable to run it without explicitly invoking bash.
### My Solve
Flag:pwn.college{s8Y_jL2W_mLsZCd-lwp7HpKONrS.QX0cjM1wCO5kjNzEzW}
```
hacker@chaining~executable-shell-scripts:~$ echo /challenge/solve > x.sh
hacker@chaining~executable-shell-scripts:~$ ~/x.sh
bash: /home/hacker/x.sh: Permission denied
hacker@chaining~executable-shell-scripts:~$ chmod u+x /challenge/solve
chmod: changing permissions of '/challenge/solve': Operation not permitted
hacker@chaining~executable-shell-scripts:~$ chmod +x x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{s8Y_jL2W_mLsZCd-lwp7HpKONrS.QX0cjM1wCO5kjNzEzW}
hacker@chaining~executable-shell-scripts:~$
```
I started this challenge by redirecting the output of /challenge/solve to a shell script called x.sh and ran chmod +x x.sh to make the command in the shell script
executable. I finally typed ./x/sh which is a relative path to invoke the program in the shell script to get the flag without running the bash command.
### What I learned
When we invoke bash script.sh, we are, of course launching the bash command with the script.sh argument. 
This tells bash to read its commands from script.sh instead of standard input, and thus our shell script is executed.

It turns out that you can avoid the need to manually invoke bash.
If our shell script file is executable (recall File Permissions), we can simply invoke it via its relative or absolute path.
### References
Instructions in pwn.college website


### Task 7
For this challenge, we need to create a script at /home/hacker/solve.sh that has a proper shebang and outputs "hack the planet".
Firstly, we need to make it executable, then run /challenge/run to verify our script works correctly
### My Solve
Flag:pwn.college{sW08Ybd1fdWgVdWkwGaab3caT0l.0VOzMDOxwCO5kjNzEzW}
```
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~understanding-shebangs:~$ echo echo hack the planet >> solve.sh
hacker@chaining~understanding-shebangs:~$ chmod +x solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{sW08Ybd1fdWgVdWkwGaab3caT0l.0VOzMDOxwCO5kjNzEzW}

hacker@chaining~understanding-shebangs:~$
```
I typed the echo '#!/bin/bash' > solve.sh command to create a file with shebang first and then redirected the output of echo command of echo hack the planet
so that the command echo "hack the planet" is stored in the file and by running it we can execute echo "hack the planet" to print the flag contained in 
hack the planet. For that, I changed the permission of solve.sh previously to make it executable.
### What I learned
When a program is invoked in Linux, the Linux kernel first inspects the file to determine how it should be run. This does NOT use the extension (which is why we don't have to name our shell scripts with a .sh extension, or our Python scripts with a .py extension, or so on). 
Rather, Linux looks at the first few bytes of the file for this information.
There are a bunch of different types of programs, but if the program file starts with the characters #! (often termed a "shebang"), 
Linux treats the file as an interpreted program, and the contents of the rest of the line as the path to the interpreter. 
It then invokes the interpreter with the path to the program file as its only argument.
### References
Instructions in pwn.college website


### Task 8
For this challenge, we need to write a script at /home/hacker/solve.sh such that:
1)Takes two arguments
2)Outputs them in REVERSE order (second argument first, then the first argument)
### My Solve
Flag:pwn.college{UmfJZvDbCCMjSDsOndKEx_Jk_9J.0VNzMDOxwCO5kjNzEzW}
```
hacker@chaining~scripting-with-arguments:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~scripting-with-arguments:~$ echo 'echo "$2 $1"' >> solve.sh
hacker@chaining~scripting-with-arguments:~$ chmod +x solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{UmfJZvDbCCMjSDsOndKEx_Jk_9J.0VNzMDOxwCO5kjNzEzW}
hacker@chaining~scripting-with-arguments:~$
```
In this challenge, just as the previous task I ran echo '#!/bin/bash' > solve.sh to make a file with shebangs and I ran echo 'echo "$2 $1"' >> solve.sh so that the
The script can access these arguments(in this case, the first and the second argument) using special variables and print them in the reverse order via the echo command.
Then, I granted permission to the script to execute /challenge/run using chmod +x solve.sh.
### What I learned
The script can access these arguments using special variables:

$1 contains the first argument ("hello")
$2 contains the second argument ("world")
$3 would contain the third argument (if there had been one)
...and so on
### References
Instructions in pwn.college website


### Task 9
For this challenge, we need to write a script at /home/hacker/solve.sh such that:
Takes one argument
If the argument is "pwn", output "college"
For any other input, output nothing
### My Solve
Flag:pwn.college{YGW_9LqdmwQAHLWAqYdSgyEXm6f.0lNzMDOxwCO5kjNzEzW}
```
hacker@chaining~scripting-with-conditionals:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'if [ "$1" = "pwn" ]; then' >> solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo '  echo "college"' >> solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'fi' >> solve.sh
hacker@chaining~scripting-with-conditionals:~$ chmod +x solve.sh
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{YGW_9LqdmwQAHLWAqYdSgyEXm6f.0lNzMDOxwCO5kjNzEzW}
hacker@chaining~scripting-with-conditionals:~$
```
Firstly, I made a file with shebangs afterwards which, I used the if condition such that if the first argument is pwn then it appends the output of echo college
The echo fi is the terminator of the if statement. Then, I enabled the permission of execution of solve.sh and finally ran /challenge/run.
### What I learned
In bash, we can use if statements to make decisions:

if [ "$1" == "ping" ]
then
    echo "pong"
fi
The above, in English, is if the first argument is "ping", print out "pong". The syntax is somewhat unforgiving for a few reasons. 
First, we must have spaces after if (if you're used to a language like C, this is different), after [, and before ]. 
Second, if, then, and fi must all be on different lines (or separated by semicolons); you can't lump them into the same statement. 
It's also a bit weird: instead of endif or end or something like that, the terminator of the if statement is fi (if backwards).
### References
Instructions in pwn.college website






 













































