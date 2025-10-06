# Untangling Users
### Task 1
This challenge asks to access the root by passing the password hack-the-planet to the su command as this challenge requires a 
root password to access the root directory /home/hacker.
### My Solve
Flag:pwn.college{kIweONCIcvFfMNeX-Aal9j2_RC5.QX1UDN1wCO5kjNzEzW}
```
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{kIweONCIcvFfMNeX-Aal9j2_RC5.QX1UDN1wCO5kjNzEzW}
root@users~becoming-root-with-su:/home/hacker#
```
I passed the su command as instructed and typed the password hack-the-planet to access the root directory and used the cat
command to display the flag.
### What I learned
It's not just hackers that need to become root. 
Oftentimes, we, as the owner of our computer, need to use root access to administer it. 
Becoming root is a fairly common action that Linux users take, 
and there are two utilities that exist for this purpose: su and sudo.
This challenge, covers the older one, su (the substitute user command). 
This is not typically used to elevate to root access anymore, 
but it is an elegant utility from a more civilized time.
The su command became obsolute as modern systems very rarely have root passwords, 
and different mechanisms are used to grant administrative access.
### References
Instructions in pwn.college website.


### Task 2
This challenge asks to substitute to a different user named zardus using the su command(substitute user) by providing
a given password
### My Solve
Flag:pwn.college{oiUaNJD55q7dYbQhMW86286YH9M.QX2UDN1wCO5kjNzEzW}
```
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{oiUaNJD55q7dYbQhMW86286YH9M.QX2UDN1wCO5kjNzEzW}
zardus@users~other-users-with-su:/home/hacker$
```
I simply ran the su command with the argument of the username I want to switch to by typing the giving password
dont-hack-me to get the flag.
### What I learned
With no arguments, su will start a root shell (after authenticating with root's password). 
However, we can also give a username as an argument to switch to that user instead of root.
### References
Instructions in pwn.college website.


### Task 3
This challenge asks to access the leak /etc/shadow (in /challenge/shadow-leak) by using John The Ripper to crack
the password of the user zardus
### My Solve
Flag:
```
hacker@users~cracking-passwords:~$ cat /challenge/shadow-leak
root:*:20182:0:99999:7:::
daemon:*:20182:0:99999:7:::
bin:*:20182:0:99999:7:::
sys:*:20182:0:99999:7:::
sync:*:20182:0:99999:7:::
games:*:20182:0:99999:7:::
man:*:20182:0:99999:7:::
lp:*:20182:0:99999:7:::
mail:*:20182:0:99999:7:::
news:*:20182:0:99999:7:::
uucp:*:20182:0:99999:7:::
proxy:*:20182:0:99999:7:::
www-data:*:20182:0:99999:7:::
backup:*:20182:0:99999:7:::
list:*:20182:0:99999:7:::
irc:*:20182:0:99999:7:::
gnats:*:20182:0:99999:7:::
nobody:*:20182:0:99999:7:::
_apt:*:20182:0:99999:7:::
systemd-timesync:*:20357:0:99999:7:::
systemd-network:*:20357:0:99999:7:::
systemd-resolve:*:20357:0:99999:7:::
mysql:!:20357:0:99999:7:::
messagebus:*:20357:0:99999:7:::
sshd:*:20357:0:99999:7:::
hacker::20357:0:99999:7:::
zardus:$6$nOuxwa53x/eKWEV9$OC6yv4UJBUSfKF/CpH60wT3pfMeTtF5vXZKUJbcZZHEqhYbiUbnhdOmbktLsgvM223iKlo9Gc5zbaWj.5wQMq/:20367:0:99999:7:::
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Created directory: /home/hacker/.john
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04906g/s 285.7p/s 285.7c/s 285.7C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ john --show /challenge/shadow-leak
hacker:NO PASSWORD:20357:0:99999:7:::
zardus:aardvark:20367:0:99999:7:::

2 password hashes cracked, 0 left
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{QaGMOYwc5Qp5qTu0H1ODrrjU1xW.QX3UDN1wCO5kjNzEzW}
zardus@users~cracking-passwords:/home/hacker$
```
For accessing a leak of /etc/shadow I ran cat /challenge/shadow-leak(given in the challenge). Nextly, I used
the famous John The Ripper tool to crack the password of the user zardus. After successfully doing so, I switched
to the user zardus by typing the password aardvark and finally ran /challenge/run to get the flag.
### What I learned
When we enter a password for su, it compares it against the stored password for that user. 
These passwords used to be stored in /etc/passwd, 
but because /etc/passwd is a globally-readable file, this is not good for passwords, these were moved to /etc/shadow.
Separated by :s, the first field of each line is the username and the second is the password in a leak of /etc/shadow
A value of * or ! functionally means that password login for the account is disabled, and 
a blank field means that there is no password.
If a hacker gets their hands on a leaked /etc/shadow, they can start cracking passwords and wreaking havoc. 
The cracking can be done via the famous John the Ripper.
### References
Instructions in the pwn.college website.


### Task 4
This straight forward challenge provides us sudo access which we are told to use to read the flag,
### My Solve
Flag:pwn.college{I12-YXe2-Hw1gBjR7CCJTSj2O_z.QX4UDN1wCO5kjNzEzW}
```
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{I12-YXe2-Hw1gBjR7CCJTSj2O_z.QX4UDN1wCO5kjNzEzW}
hacker@users~using-sudo:~$
```
I simply ran cat /flag prepended with the sudo command to print the flag.
### What I learned
In the olden days, a typical Linux system had a root password that administrators would use to su to root 
(after logging into their account with their normal account password). But root passwords are a pain to maintain, 
they (or their hashes!) can leak, and they don't lend themselves well to larger environments (e.g., fleets of servers).
To address this, in recent decades, the world has moved from administration via su to administration via sudo 
(Fun Fact: sudo originally stood for superuser do, but has changed to "su 'do'",
and because su stands for "substitute user", the current meaning of sudo is "substitute user, do").
Unlike su, which defaults to launching a shell as a specified user, sudo defaults to running a command as root
Unlike su, which relies on password authentication, sudo checks policies to determine whether the user is authorized to run 
commands as root.
### References
Instructions in the pwn.college website.




























