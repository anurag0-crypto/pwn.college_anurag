# File Globbing
### Task 1
This challenge asks to change the directory to /challenge with an argument of at most 4 characters provided to the cd command.
### My Solve 
Flag:pwn.college{AvUcQz3ewXqz3HYjXa6sUwC7nW9.QXxIDO0wCO5kjNzEzW}
```
This challenge resets your working directory to /home/hacker unless you change
directory properly...
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /*l*
bash: cd: too many arguments
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{AvUcQz3ewXqz3HYjXa6sUwC7nW9.QXxIDO0wCO5kjNzEzW}
hacker@globbing~matching-with-:/challenge$
```
I gave an argument initially of /*l* which did not change the directory as there exists many directories with a letter l between their respective directory names.
Then, I gave a more direct and specific argument of /ch* which changed the directory to a directory starting with ch in its name. Hence, I successfully changed the directory to /challenge with using a cd command, of at most 4 characters. 
Finally, I typed /challenge/run to obtain the flag.
### What I learned
When the shell encounters a * character in any argument, the shell will treat it as a "wildcard" and try to replace that argument with any files that match the pattern.
Significance of * being passed in the argument expands to the corresponding matching directory name.
### References
Instructions in pwn.college.


### Task 2
This challenge clearly asks to change the directory to /challenge using ? character in replacement of c and l.
### My Solve
Flag:pwn.college{csOhAzhYB_oYsfBmGQdgd20uFW5.QXyIDO0wCO5kjNzEzW}
```
This challenge resets your working directory to /home/hacker unless you change
directory properly...
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{csOhAzhYB_oYsfBmGQdgd20uFW5.QXyIDO0wCO5kjNzEzW}
hacker@globbing~matching-with-:/challenge$
```
I ran cd /?ha??enge which changed the working directory to /challenge and ran /challenge/run to get the flag.
### What I learned
When the shell encounters a ? character in any argument, the shell will treat it as a single-character wildcard. This works like *, but only matches one character.
### References
Instructions in pwn.college.


### Task 3
This challenge asks to change the directory to /challenge/files and run /challenge/run with an argument that bracket globs file_a,file_b,file_s,file_h.
### My Solve
Flag:pwn.college{IeczvcQfeQSbpwFRbvpqi5jlIR-.QXzIDO0wCO5kjNzEzW}
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[abhs]
You got it! Here is your flag!
pwn.college{IeczvcQfeQSbpwFRbvpqi5jlIR-.QXzIDO0wCO5kjNzEzW}
hacker@globbing~matching-with-:/challenge/files$
```
I changed the directory to /challenge/files as mentioned in the challenge and ran /challenge/files file_[abhs] to match the 4 above files mentioned to get the flag.
### What I learned
The square brackets are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. For example, [pwn] will match the character p, w, or n.
### References
Instructions in pwn.college.


### Task 4
This challenge asks to run /challenge/run from the home directory using an argument that globs into the absolute path of the 4 respective files as mentioned.
### My Solve
Flag:pwn.college{gi9GA8__Rf2REMJp7_rVPr6rfBf.QX0IDO0wCO5kjNzEzW}
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[abhs]
You got it! Here is your flag!
pwn.college{gi9GA8__Rf2REMJp7_rVPr6rfBf.QX0IDO0wCO5kjNzEzW}
hacker@globbing~matching-paths-with-:~$
```
I ran the /challenge/run /challenge/files/file_[abhs] command from the home directory,where the argument globs into absolute path of the 4 respective files as mentioned to obtain the flag.
### What I learned
Globbing happens on a path basis, so we can expand entire paths with our globbed arguments.
### References
Instructions in pwn.college website.


### Task 5
This challenge asks to enter a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p, as an argument to 
/challenge/run after changing the directory to /challenge/files.
### My Solve 
Flag:pwn.college{Mf9jWiRla_T-l6DVPcpNx2RYGIO.0lM3kjNxwCO5kjNzEzW}
```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{Mf9jWiRla_T-l6DVPcpNx2RYGIO.0lM3kjNxwCO5kjNzEzW}
hacker@globbing~multiple-globs:/challenge/files$
```
In this challenge,as it requires (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p, we can use *p*. I used cd to change directory to /challenge/files and ran /challenge/run *p* to get the flag.
### What I learned
Problem Solving
### References
Instructions in pwn.college.


### Task 6
To pass an argument that will glob files named challenging,pwning,educational with an argument of at most 6 characters to /challenge/run.
### My Solve
Flag:pwn.college{cfboD_OR0veWN-0Vi_-UzbCLVFM.QX1IDO0wCO5kjNzEzW}
```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *n[gp]
Your expansion did not expand to the requested files (challenging, educational,
pwning). Instead, it expanded to:
amazing challenging laughing pwning thrilling uplifting
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run *[ing]*
Error: your argument is too long! It must be 6 characters or less.
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{cfboD_OR0veWN-0Vi_-UzbCLVFM.QX1IDO0wCO5kjNzEzW}
hacker@globbing~mixing-globs:/challenge/files$
```
I tried a subset of similar characters present in challenging,pwning,educational repetitively to get the respective command to glob only
the three files named challenging,pwning,educational specifically. Until, I realized that only these files start with c,p and e respectively in
the /challenge/files directory. I ran /challenge/run [cep]* to get the flag.
### What I learned
Problem Solving.
### References
Instructions in pwn.college.


### Task 7
The challenge asks to filter out files that do not start with p,w,n.
### My Solve
Flag:pwn.college{0DsIRDvJ2uUp9k7rXizY8rzgon9.QX2IDO0wCO5kjNzEzW}
```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{0DsIRDvJ2uUp9k7rXizY8rzgon9.QX2IDO0wCO5kjNzEzW}
hacker@globbing~exclusionary-globbing:/challenge/files$
```
Similar to the previous task, I ran /challenge/run [^pwn]* to get the flag. Here, ^ lists the flags which do not start with p,w,n.
### What I learned
Sometimes, we want to filter out files in a glob. [] helps us do this. If the first character in the brackets is a !
or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed.
^ specifies the opposite of the command,i.e works as an inversion of the command.
### References
Instructions in pwn.college.


### Task 8
This challenge asks to display the flag which has been copied to the /challenge/pwncollege directory but to read it using the TAB key to autocomplete
the name of the file.
### My Solve
Flag:pwn.college{sqxMlDW2hGedsb2hMArrspjHgom.0FN0EzNxwCO5kjNzEzW}
```
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​
.bash_history       COLLEGE             college             intercepted_output  pwn
.config/            PWN                 errors.log          myflag              the-flag
.lesshst            a                   instructions        not-the-flag
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ the-flag
pwn.college{sqxMlDW2hGedsb2hMArrspjHgom.0FN0EzNxwCO5kjNzEzW}
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
hacker@globbing~tab-completion:~$
```
I typed cat /challenge/pwn and pressed the TAB key which successfully auto completed the directory to /challenge/pwncollege.
Then, after pressing the TAB key multiple times it listed out the possible file names I can specify as an argument to the
command. I typed cat /challenge/pwncollege the-flag to get the flag.
### What I learned
A safer alternative when we are trying to specify a specific target is tab completion. If we hit tab in the shell, it'll try to figure out what we are going to type and automatically complete it. Auto-completion is super useful, and this challenge explores its use in specifying files.
Usage of the TAB key to autocomplete the name of the file.
### References
Instructions in pwn.college.


### Task 9
This challenge asks us to type /challenge/files/p and hit tab two times to display all the options of the name of the auto completed file.
### My Solve
Flag:pwn.college{olnZB8kMEO9uKk1-fJeCHcL1BvC.0lN0EzNxwCO5kjNzEzW}
```
hacker@globbing~multiple-options-for-tab-completion:~$ cd /challenge/files
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwn
pwn                    pwn-the-planet         pwncollege-flag        pwncollege-flyswatter
pwn-college            pwncollege-family      pwncollege-flamingo    pwncollege-hacking
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$ cat pwncollege-flag
pwn.college{olnZB8kMEO9uKk1-fJeCHcL1BvC.0lN0EzNxwCO5kjNzEzW}
hacker@globbing~multiple-options-for-tab-completion:/challenge/files$
```
After switching to the /challenge/files directory using cd command,I hit the TAB two times to get a variety of options of the file name. I used the file name pwncollege-flag to most suitably fit the autocompleted name and and finally ran cat pwncollege-flag to get the flag.
### What I learned
By default bash will auto-expand until the first point when there are multiple options (in this case, fl). When you hit tab a second time, it'll print out those options. Other shells and configurations, instead, will cycle through the options.
### References
Instructions in pwn.college.


### Task 10
This challenge asks to invoke a command starting with pwncollege and hit the TAB to autocomplete the command.
### My Solve
Flag:pwn.college{Ac6vOCAEGLXKE_4SWbrYtBRJ7aD.0VN0EzNxwCO5kjNzEzW}
```
hacker@globbing~tab-completion-on-commands:~$ pwncollege-380
.bash_history       COLLEGE             college             intercepted_output  pwn
.config/            PWN                 errors.log          myflag              the-flag
.lesshst            a                   instructions        not-the-flag
hacker@globbing~tab-completion-on-commands:~$ pwncollege-380
Correct! Here is your flag:
pwn.college{Ac6vOCAEGLXKE_4SWbrYtBRJ7aD.0VN0EzNxwCO5kjNzEzW}
hacker@globbing~tab-completion-on-commands:~$
```
I typed pwncollege in terminal and hit TAB which autocompleted the command to pwncollege-380. I simply typed it and pressed enter to get the flag.
### What I learned
TAB can also be used to autocomplete commands.
### References
Instructions in pwn.college.





















































































