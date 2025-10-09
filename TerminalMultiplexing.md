# Terminal Multiplexing
### Task 1
This challenge asks to launch the screen program which creates virtual terminals inside the terminal.
### My Solve
Flag:pwn.college{sZ_M2ybXbYBT6doKBQzQYFV5Udp.0VN4IDOxwCO5kjNzEzW}
```
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{sZ_M2ybXbYBT6doKBQzQYFV5Udp.0VN4IDOxwCO5kjNzEzW}
hacker@terminal-multiplexing~launching-screen:~$
```
I simply ran the screen program to launch a virtual terminal inside the terminal.
### What I learned
screen is a program that creates virtual terminals inside the terminal.
It's somewhat like having multiple browser tabs, but for the command line
### References
Instructions in pwn.college website


### Task 2
For this challenge, we need to:
Launch screen
Detach from it.
Run /challenge/run (this will secretly send the flag to your detached session!)
Reattach to see your prize
### My Solve
Flag:pwn.college{sSpkvpUQZNvEPMnJdZfIobKJfBi.0lN4IDOxwCO5kjNzEzW}
```
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 199.pts-4.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 199.pts-4.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
```
In virtual terminal...
```
hacker@terminal-multiplexing~detaching-and-attaching:~$
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{sSpkvpUQZNvEPMnJdZfIobKJfBi.0lN4IDOxwCO5kjNzEzW}
Yes! Flag is: pwn.college{sSpkvpUQZNvEPMnJdZfIobKJfBi.0lN4IDOxwCO5kjNzEzW}
hacker@terminal-multiplexing~detaching-and-attaching:~$
```
I simply ran screen initially to launch a screen. I detached the screen by typing Ctrl-A and then d. Then, I ran /challenge/run
to write the flag to the detached terminal. Finally, I ran screen -r to reattach the virtual terminal and obtain the flag.
### What I learned
We can detach a virtual terminal by pressing Ctrl-A + d and reattach the screen by running screen -r.
### References
Instructions in pwn.college website.


### Task 3
In this challenge, there are three screen sessions. One of them contains the flag. The other two are decoys. I need to find
the correct session to obtain the flag.
### My Solve
Flag:pwn.college{sIQBq4YOdrz95zwUuLN0wlA72_f.01N4IDOxwCO5kjNzEzW}
```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
        180.pts-2.terminal-multiplexing~launching-screen        (Remote or dead)
        199.pts-4.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_5700b1b2926e3be7    (Detached)
        147.session_cd384463419f0954    (Detached)
        150.session_c51925c10cff5a35    (Detached)
5 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 144
[detached from 144.session_5700b1b2926e3be7]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147
[detached from 147.session_cd384463419f0954]
hacker@terminal-multiplexing~finding-sessions:~$
```
Terminal with PID 144:
```
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Nothing here! Try another session.'
Nothing here! Try another session.
hacker@terminal-multiplexing~finding-sessions:~$
```
Terminal with PID 147:
```
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{sIQBq4YOdrz95zwUuLN0wlA72_f.01N4IDOxwCO5kjNzEzW}
pwn.college{sIQBq4YOdrz95zwUuLN0wlA72_f.01N4IDOxwCO5kjNzEzW}
hacker@terminal-multiplexing~finding-sessions:~$
```
I ran screen -ls to list all the virtual terminal sessions. I reattached three of the deattached sessions one by one
using their respective PID to finally obtain the flag in the terminal with PID 147. I specified the PID in the command
screen -r <PID> to reattach that particular virtual terminal.
### What I learned
We can view multiple virtual terminal sessions by running screen -ls and their respective status(e.g- detached,dead,etc.)
We can reattach a particular virtual terminal by specifying its name or PID with the screen -r argument.
### References
Instructions in pwn.college website


### Task 4
For this challenge, there is a screen session with two windows:
Window 0 has... well, you'll have to switch there to find out!
Window 1 has a welcome message
I have to find the flag in either of these two windows.
### My Solve
Flag:pwn.college{IsyMBVlo-8QQEWJJAuZIcqnY-KF.0FO4IDOxwCO5kjNzEzW}
```
hacker@terminal-multiplexing~switching-windows:~$ screen -r
```
In window 0...
```
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{IsyMBVlo-8QQEWJJAuZIcqnY-KF.0FO4IDOxwCO5kjNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{IsyMBVlo-8QQEWJJAuZIcqnY-KF.0FO4IDOxwCO5kjNzEzW}
hacker@terminal-multiplexing~switching-windows:~$
```
I simply ran screen -r and switched to window 0 by pressing Ctrl-A 0 to obtain the flag(mentioned in the welcome message)
### What I learned
Various shortcuts for virtual terminals:
These windows are handled with different keyboard shortcuts, all starting with Ctrl-A:

Ctrl-A c - Create a new window
Ctrl-A n - Next window
Ctrl-A p - Previous window
Ctrl-A 0 through Ctrl-A 9 - Jump directly to window 0-9
Ctrl-A " - bring up a selection menu of all of the windows
### References
Instructions in pwn.college website


### Task 5
This task is similar to task 2 except that it requires the tmux command for the same operations and has slight differences
in its commands of deattaching and reattaching terminals.
### My Solve
Flag:pwn.college{oMprBIT0HenrXfTDMChHuDUfRrX.0VO4IDOxwCO5kjNzEzW}
```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 1)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
```
In virtual terminal...
```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ 11;rgb:0c0c/0c0c/0c0c echo Congratulations, here is your flag: pwn.college{oMprBIT0HenrXfTDMChHuDUfRrX.0VO4IDOxwCO5kjNzEzW}
```
I simply did the same as task 2, but for attaching the terminal I ran Ctrl-B + d and for reattaching I ran tmux attach
### What I learned
tmux (terminal multiplexer) is screen's younger, more modern cousin. It does all the same things but with 
some different key bindings.
For example, Instead of Ctrl-A, tmux uses Ctrl-B as its command prefix.
The commands also differ:

tmux ls - List sessions
tmux attach or tmux a - Reattach to session
### References
Instructions in pwn.college website


### Task 6
This challenge entails a tmux session with two windows:

Window 0 has the flag!
Window 1 has your warm welcome.
I have switch to window 0 to obtain the flag.
### My Solve
Flag:pwn.college{4K_2iCxK39fh6xHs6JAOcFCJE4V.0FM5IDOxwCO5kjNzEzW}
```
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux attach
```
In virtual terminal after switching to window 0:
```
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{4K_2iCxK39fh6xHs6JAOcFCJE4V.0FM5IDOxwCO5kjNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{4K_2iCxK39fh6xHs6JAOcFCJE4V.0FM5IDOxwCO5kjNzEzW}
hacker@terminal-multiplexing~switching-windows-tmux:~$
```
I simply ran tmux attach to create a window and ran Ctrl-B 0 to switch to the window 0 to get the flag.
### What I learned
Just like screen, tmux has windows. The key combos are different, but the concept is the same:
Ctrl-B c - Create a new window
Ctrl-B n - Next window
Ctrl-B p - Previous window
Ctrl-B 0 through Ctrl-B 9 - Jump to window 0-9
Ctrl-B w - See a nice window picker
### References
Instructions in pwn.college website



















