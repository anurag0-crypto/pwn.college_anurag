# Perceiving Permissions
### Task 1
This challenge asks to change the ownership of the /flag file from root to the hacker user using the chown command.
### My Solve
Flag:pwn.college{wJjX6Fgv5c_WAFL5fIeWso9gQzl.QXxEjN0wCO5kjNzEzW}
```
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{wJjX6Fgv5c_WAFL5fIeWso9gQzl.QXxEjN0wCO5kjNzEzW}
hacker@permissions~changing-file-ownership:~$
```
In this challenge, I simply use the chown command to change the ownership of the /flag file from root to the hacker user and use the cat command to display the /flag.
### What I learned
Every file in Linux is owned by a user on the system. Most often, in our day-to-day life, that user is the user we log in as every day.
On a shared system (such as in a computer lab), there might be many people with different user accounts, all with their own files in their own home directories.
But even on a non-shared system (such as your personal PC), Linux still has many "service" user accounts for different tasks.
The two most important user accounts are:
Our user account! On pwn.college, this is the hacker user, regardless of what our username is.
Root. This is the administrative account and, in most security situations, the ultimate prize. 
If we take over the root user, we have  almost certainly achieved our hacking objective!
The chown command can be used to change the ownership of a particular file. The format is chown "username" "filename"
### References
Instructions in pwn.college website.


### Task 2
This challenge asks to change the group ownership of the flag file from root to hacker using the chgrp command to access the flag file
### My Solve
Flag:pwn.college{MdWcndZlOeWqIXWKDphOrvi_1nh.QXxcjM1wCO5kjNzEzW}
```
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{MdWcndZlOeWqIXWKDphOrvi_1nh.QXxcjM1wCO5kjNzEzW}
hacker@permissions~groups-and-files:~$
```
I ran the chgrp command with the username "hacker" and the filename "/flag" to change the group ownership of the flag and finally access it using the cat command.
### What I learned
Files have both an owning user and group. A group can have multiple users in it, and a user can be a member of multiple groups.
We can check what groups we are part of with the id command.In this challenge, the flag file is owned by the root user and the root group, and the hacker user
is neither the root user nor a member of the root group, so the file cannot be accessed. Luckily, group ownership can be changed with the chgrp (change group) command! 
Unless you have write access to the file and membership in the new group, this typically requires root access.The format is chgrp "username" "filename"
### References
Instructions in the pwn.college website.


### Task 3
This challenge has randomized the group name which I need to find out using the id command which displays the groups I am part of and then change ownership of the
group to access the flag.
### My Solve
Flag:pwn.college{sznhm1QJh3gcDyC2J_FNuS0RNS2.QXycjM1wCO5kjNzEzW}
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp3765) groups=1000(grp3765)
hacker@permissions~fun-with-groups-names:~$ chgrp grp3765 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{sznhm1QJh3gcDyC2J_FNuS0RNS2.QXycjM1wCO5kjNzEzW}
hacker@permissions~fun-with-groups-names:~$
```
I ran the id command to list out the groups I am part of and hence found the randomized name of the group named grp3765. I ran chgrp grp3765 /flag to change the
group ownership of the /flag file and finally used the cat command to get the flag.
### What I learned
Problem Solving.
### References
The id command can be used to view the groups we are currently part of.


### Task 4
In this challenge,I need to change the permissions of the /flag file to read it which is owned by the root(I cannot change ownership in this challenge).
### My Solve
Flag:pwn.college{IL6MAwTXSrLq-RiZgi-Gyx3IVjs.QXzcjM1wCO5kjNzEzW}
```
hacker@permissions~changing-permissions:~$ chmod a+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{IL6MAwTXSrLq-RiZgi-Gyx3IVjs.QXzcjM1wCO5kjNzEzW}
hacker@permissions~changing-permissions:~$
```
I used the chmod command to grant permission to everyone to read the flag file specifying the mode as a+r(a for all and r for reading). After granting the permission,
I viewed the flag by the cat command.
### What I laerned
The first character represents the file type. The next nine characters are the actual access permissions of the file or directory, 
split into 3 characters denoting permissions for the owning user , 3 characters denoting the permissions for 
the owning group and 3 characters denoting the permissions that all other access (e.g., by other users and other groups) has to the file.
r - user/group/other can read the file (or list the directory)
w - user/group/other can modify the files (or create/delete files in the directory)
x - user/group/other can execute the file as a program (or can enter the directory, e.g., using `cd`)
- - nothing
 The chmod command allows us to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute.
For example, to add read access for the owning user,
we would specify a mode of u+r. write and execute access for the group and the other (or all the modes) are specified the same way.
### References
Instructions in the pwn.college website.


### Task 5
This challenge asks to use chmod to make /challenge/run executable for it to be invoked again to obtain the flag.
### My Solve
Flag:pwn.college{g5vm_r1Ew9cgT_3nk_8_wvSlyBh.QXyEjN0wCO5kjNzEzW}
```
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{g5vm_r1Ew9cgT_3nk_8_wvSlyBh.QXyEjN0wCO5kjNzEzW}
hacker@permissions~executable-files:~$
```
I ran chmod a+x /challenge/run to make /challenge/run executable for all the modes and invoked /challenge/run again to get the flag.
### What I learned
Nothing new since the last task
### References
Instructions in the pwn.college website.


### Task 6
This challenge asks to change the permissions of the /flag file according to the instructions given in each of the 8 rounds
### My Solve
Flag:pwn.college{I9akxvGasuqr0G1dI1X3W31PeTg.QXwEjN0wCO5kjNzEzW}
```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r-----
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-r /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rw-r-----
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r-----
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": r--r-----
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rw----
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+w,g+w /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": rw-rw----
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxrwx-wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x,g+x,o+wx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": rwxrwx-wx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr-x-wx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-w,g-w /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": r-xr-x-wx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--r-x-wx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-x /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": r--r-x-wx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr-xrwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x,o+r /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": r-xr-xrwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr--r--
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-x,o-wx /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{I9akxvGasuqr0G1dI1X3W31PeTg.QXwEjN0wCO5kjNzEzW}
hacker@permissions~permission-tweaking-practice:~$
```
I simply changed the permissions of the flag accordingly to the instructions given in each round. For example, in the last round, I changed the group permission
to not be able to execute(g-x) and changed the permission of the world to not be able to write or execute(o-wx). After the 8 rounds, I enabled the permission for the
user to be able to read the /flag using chmod and obtained it using cat /flag.
### What I learned
Practice and more familiarity with changing permissions of a file.
### References
Instructions in the pwn.college website


### Task 7
This challenge is similar to previous one except here it is asked to change permissions using setting '='.
### My Solve
Flag:pwn.college{kVP-T7_so6YCluZiSHc9JHXssWY.QXzETO0wCO5kjNzEzW}
```
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w--wxr--
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=wx,o=r /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -w--wxr--
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r-x-wx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=rx,o=wx /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": r--r-x-wx
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ------rw-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=-,o=rw /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": ------rw-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w--wxrw-
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=wx,o=rw /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": -w--wxrw-
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r---w---x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=w,o=x /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": r---w---x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --x-w---x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=w,o=x /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": --x-w---x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---rw----
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=rw,o=- /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": ---rw----
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---r---wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=r,o=wx /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{kVP-T7_so6YCluZiSHc9JHXssWY.QXzETO0wCO5kjNzEzW}
hacker@permissions~permissions-setting-practice:~$
```
Similar to earlier challenge, the only difference here is that I used setting operations(=) to do the same.
For example, after 8 rounds, I set u=rwx to make the flag file readable,writable and executable.
### What I learned
In addition to adding and removing permissions, as in the previous level, chmod can also simply set permissions altogether, overwriting the old ones. This is done by using = instead of - or +. For example:

u=rw sets read and write permissions for the user, and wipes the execute permission
o=x sets only executable permissions for the world, wiping read and write
a=rwx sets read, write, and executable permissions for the user, group, and world
Additionally, we can zero out permissions with -:

chmod u=rw,g=r,o=- /challenge/pwn will set the user permissions to read and write, the group permissions to read-only, and the world permissions to nothing at all.
### References
Instructions in the pwn.college website.


### Task 8
This challenge asks to add the SUID bit to the /challenge/getroot program in order to spawn a root shell to cat the flag.
### My Solve
Flag:pwn.college{Qb9fB-RXIDacovyyIvfVYTr1ZBX.QXzEjN0wCO5kjNzEzW}
```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{Qb9fB-RXIDacovyyIvfVYTr1ZBX.QXzEjN0wCO5kjNzEzW}
root@permissions~the-suid-bit:~#
```
I ran chmod u+s /challenge/getroot to make /challenge/getroot executable with SUID.
It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user (in this case, the root user). Then, I ran /challenge/getroot to spawn a root shell and displayed
the flag using cat.
### What I learned
As we explored in the previous module, there are many cases in which non-root users need elevated access to do certain system tasks. The system admin can't be there to give them the password every time a user wanted to do a task that only root/sudoers can do. Instead, the "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.
This is actually the exact mechanism used to let the challenge programs you run read the flag or, outside of pwn.college, to enable system administration tools such as su, sudo, and so on.
As the owner of a file, we can set a file's SUID bit by using chmod:
chmod u+s [program]
Here, the s in place of x depicts that the program is executable with SUID.
### References
Instructions in the pwn.college website.

































