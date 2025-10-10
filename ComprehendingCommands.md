
# Comprehending Commands
### Task 1
This challenge asks to read the flag file using cat and hence obtain the flag.
### My Solve 
Flag:pwn.college{A9SPP_Rlaa-LSrjJWtV3tWbxShD.QXxcTN0wCO5kjNzEzW}
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{A9SPP_Rlaa-LSrjJWtV3tWbxShD.QXxcTN0wCO5kjNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$
```
I used the cat command to display the contents of the flag file and hence obtain the flag.
### What I learned
We can use cat command to read a file by specifying the file name as argument to the cat command.
### References
Instructions in pwn.college.


### Task 2
This challenge asks to read the flag from its absolute path.
### My Solve
Flag:pwn.college{wX17exKyxwFBmtiFJLNsmgxhFkS.QX5ETO0wCO5kjNzEzW}
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{wX17exKyxwFBmtiFJLNsmgxhFkS.QX5ETO0wCO5kjNzEzW}
hacker@commands~catting-absolute-paths:~$
```
I used the cat command to read flag from its absolute directory i.e  cat /flag to get the flag.
### What I learned
We can also read from a absolute path using cat command by specifying the path to the argument of cat command.
### References
Instructions in pwn.college.


### Task 3
This challenge asks to retrieve the flag from a different directory than home without using the cd command.
### My Solve
Flag:pwn.college{c6ajjHzXxgMc8nvc9OMtvgdMBFA.QXwITO0wCO5kjNzEzW}
```
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/lib/aspell/flag. Go cat it out **without** cding into that
directory!
hacker@commands~more-catting-practice:~$ cat /usr/lib/aspell/flag
pwn.college{c6ajjHzXxgMc8nvc9OMtvgdMBFA.QXwITO0wCO5kjNzEzW}
hacker@commands~more-catting-practice:~$
```
Directly invoking the cat command to the path given to the patricular directory named /usr/lib/aspell/flag
helped me fetch the flag.
### What I learned
We can directly invoke the command on a path without needing to change the working directory using cd.
### References
Instructions in pwn.college.


### Task 4
This challenge asks to search for the flag in a given file containing lines of text using the grep command.
### My Solve
Flag:pwn.college{QHeiQhlB-n2PClDWbQqzi_viMYM.QX3EDO0wCO5kjNzEzW}
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{QHeiQhlB-n2PClDWbQqzi_viMYM.QX3EDO0wCO5kjNzEzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$
```
I used the grep command with the argument of "pwn.college" to search for the flag within the file as the flag
always starts with "pwn.college".
### What I learned
Learnt the usage of the grep command and how it can be used to search for a string within lines of text
of a file.
### References
Instructions in pwn.college.


### Task 5
This challenge provides two flags: one containing 100 fake flags and one containing 100 fake flags with one real one. I am asked to find the flag using the diff command.
### My Solve
Flag: pwn.college{4cpgubrgZHqUAVVgQoC4_mbqE0n.01MwMDOxwCO5kjNzEzW}
```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
32a33
> pwn.college{4cpgubrgZHqUAVVgQoC4_mbqE0n.01MwMDOxwCO5kjNzEzW}
hacker@commands~comparing-files:~$
```
I used the diff command with the two files as arguments. As 100 fake flags of the two files are same, the diff command prints the line containing the real flag and hence the challenge is completed.
The 32a33 signifies that there is an additional line after 32 lines in second file which
contains the flag when compared to 32 lines of decoy in first file.
### What I learned
Usage of the diff command and how it can be used to compare the content of two files.
### References
Instructions in pwn.college.


### Task 6
This challenge asks to list files present in the /challenge directory to find the flag using the ls command.
### My Solve
Flag: pwn.college{wbZhpPEV0fb1ZwrBaxI6-FW9khP.QX4IDO0wCO5kjNzEzW}
```
hacker@commands~listing-files:~$ ls /challenge
14842-renamed-run-31686  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/run 14842-renamed-run-31686
bash: /challenge/run: No such file or directory
hacker@commands~listing-files:~$ /challenge/14842-renamed-run-31686
Yahaha, you found me! Here is your flag:
pwn.college{wbZhpPEV0fb1ZwrBaxI6-FW9khP.QX4IDO0wCO5kjNzEzW}
hacker@commands~listing-files:~$
```
I used the ls command on /challenge directory which I passed as an argument to the command, which listed out all non hidden files present in /challenge. I ran a file called 14842-renamed-run-31686 to get the flag.
### What I learned
Usage of the ls command and how it can be used to list files in all the directories provided to it as arguments.
### References
Instructions in pwn.college.


### Task 7
This challenge asks to create two flags in /tmp directory named pwn and college and run /challenge/run to get the flag.
### My Solve
Flag: pwn.college{8SORjdaYWese_s3JsugUXBb1rb_.QXwMDO0wCO5kjNzEzW}
```
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{8SORjdaYWese_s3JsugUXBb1rb_.QXwMDO0wCO5kjNzEzW}
hacker@commands~touching-files:/tmp$
```
I used cd command to change the directory to /tmp and used the touch command to create two flags pwn and college. I finally ran /challenge/run to get the flag.
### What I learned
Usage of the touch command and that is used to create files, the file name is give as argument to the touch command.
### References
Instructions in pwn.college.


### Task 8
This challenge asks me to remove the delete_me file from my home directory.
### My Solve
Flag: pwn.college{AVUF9BHqcBbSOqLcGkPJ2jANMYy.QX2kDM1wCO5kjNzEzW}

I used the rm command to delete the delete_me file and ran /challenge/check command to obtain the flag.
```
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge//check
Excellent removal. Here is your reward:
pwn.college{AVUF9BHqcBbSOqLcGkPJ2jANMYy.QX2kDM1wCO5kjNzEzW}
hacker@commands~removing-files:~$
```
### What I learned
Usage of the rm command and how it is used to delete files specifiying the file name to its argument.
### References
Instructions in pwn.college.


### Task 9
This challenge asks to move /flag file to /tmp/hack-the-planet.
### My Solve
Flag: pwn.college{AVUF9BHqcBbSOqLcGkPJ2jANMYy.QX2kDM1wCO5kjNzEzW}
```
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{gE8LitQ-jQVIDpc6pqa3lS7756o.0VOxEzNxwCO5kjNzEzW}
```
I used the mv command with two arguments /flag and /tmp/hack-the-planet to move flag file directly. The first
argument is the file name of the file which will be moved and the second argument is the path it will be moved
into.
### What I learned
Usage of the mv command and that is used to move files directly from the current working directory to the mentioned
path in its second argument.
### References
Instructions in pwn.college.


### Task 10
This challenge asks to find the flag present in the hidden directory.
### My Solve
Flag: pwn.college{Imk2bIMjj5K2NbouKnrrkDbEqAa.QXwUDO0wCO5kjNzEzW}
```
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv          bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-243963014401  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .flag-243963014401
pwn.college{Imk2bIMjj5K2NbouKnrrkDbEqAa.QXwUDO0wCO5kjNzEzW}
hacker@commands~hidden-files:/$
```
I used cd / to change the directory to / and ran the ls -a command to list the hidden files present as well in the directory.(-a is a special argument to the ls command)
I found a . prepended flag file which I ran using the cat command to get the necessary flag.
### What I learned
Usage of the ls -a command and how -a is a special argument used to list the hidden files with the visible
files as well.
### References
Instructions in pwn.college.


### Task 11
This challenge asks to find the flag by repeated procedure of looking about clues by changing the directory using cd and listing files in that directory to look for clues
and head to the next directory and so on...
### My Solve
Flag:  pwn.college{U_TVpwFIZlak0VpsZtdSTSZeGja.QX5IDO0wCO5kjNzEzW}
```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -la
total 80
drwxr-xr-x    1 root root 4096 Oct  1 09:10 .
drwxr-xr-x    1 root root 4096 Oct  1 09:10 ..
-rwxr-xr-x    1 root root    0 Oct  1 09:04 .dockerenv
-rw-r--r--    1 root root  213 Oct  1 09:04 DOSSIER
lrwxrwxrwx    1 root root    7 Apr  4 02:03 bin -> usr/bin
drwxr-xr-x    2 root root 4096 Apr 15  2020 boot
drwxr-xr-x    1 root root 4096 Oct  1 09:04 challenge
drwxr-xr-x    6 root root  380 Oct  1 09:04 dev
drwxr-xr-x    1 root root 4096 Oct  1 09:04 etc
-r--------    1 root root   60 Oct  1 09:04 flag
drwxr-xr-x    1 root root 4096 Sep 26 17:24 home
lrwxrwxrwx    1 root root    7 Apr  4 02:03 lib -> usr/lib
lrwxrwxrwx    1 root root    9 Apr  4 02:03 lib32 -> usr/lib32
lrwxrwxrwx    1 root root    9 Apr  4 02:03 lib64 -> usr/lib64
lrwxrwxrwx    1 root root   10 Apr  4 02:03 libx32 -> usr/libx32
drwxr-xr-x    2 root root 4096 Apr  4 02:03 media
drwxr-xr-x    2 root root 4096 Apr  4 02:03 mnt
drwxr-xr-x    1 root root   16 Oct 26  2024 nix
drwxr-xr-x    1 root root 4096 Sep 26 17:24 opt
dr-xr-xr-x 2850 root root    0 Oct  1 09:04 proc
drwx------    1 root root 4096 Sep 26 17:24 root
drwxr-xr-x    1 root root 4096 Oct  1 09:04 run
lrwxrwxrwx    1 root root    8 Apr  4 02:03 sbin -> usr/sbin
drwxr-xr-x    2 root root 4096 Apr  4 02:03 srv
dr-xr-xr-x   13 root root    0 Aug 27 03:13 sys
drwxrwxrwt    1 root root 4096 Oct  1 09:04 tmp
drwxr-xr-x    1 root root 4096 Sep 26 17:09 usr
drwxr-xr-x    1 root root 4096 Sep 26 17:08 var
hacker@commands~an-epic-filesystem-quest:/$ cat DOSSIER
Tubular find!
The next clue is in: /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ ls -la
total 24
drwxr-xr-x 1 root   root   4096 Oct  1 09:04 .
drwxr-xr-x 1 root   root   4096 Sep 26 17:09 ..
-rw-r--r-- 1 hacker hacker  202 Oct  1 09:04 ALERT
drwxr-xr-x 2 root   root   4096 Sep 26 17:09 Bold
drwxr-xr-x 2 root   root   4096 Sep 26 17:09 Regular
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ cat ALERT
Tubular find!
The next clue is in: /usr/share/locale/tig

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ cat /usr/share/locale/tig
cat: /usr/share/locale/tig: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ ls -la  /usr/share/locale/tig
total 20
drwxr-xr-x 1 root   root   4096 Oct  1 09:04 .
drwxr-xr-x 1 root   root   4096 Sep 26 17:09 ..
-rw-r--r-- 1 hacker hacker  205 Oct  1 09:04 CLUE-TRAPPED
drwxr-xr-x 2 root   root   4096 Sep 26 17:08 LC_MESSAGES
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ cat  CLUE-TRAPPED
cat: CLUE-TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ cat /usr/share/locale/tig/CLUE-TRAPPED
Lucky listing!
The next clue is in: /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/TeX/Greek

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/STIX/IntegralsUpSm$ cd /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/TeX/Greek
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/TeX/Greek$ ls -la
total 32
drwxr-xr-x 1 root   root   4096 Oct  1 09:04 .
drwxr-xr-x 1 root   root   4096 Sep 26 17:09 ..
drwxr-xr-x 2 root   root   4096 Sep 26 17:09 Bold
drwxr-xr-x 2 root   root   4096 Sep 26 17:09 BoldItalic
drwxr-xr-x 2 root   root   4096 Sep 26 17:09 Italic
-rw-r--r-- 1 hacker hacker  195 Oct  1 09:04 REVELATION
drwxr-xr-x 2 root   root   4096 Sep 26 17:09 Regular
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/TeX/Greek$ cat REVELATION
Lucky listing!
The next clue is in: /usr/share/doc/liblrcalc1

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/TeX/Greek$ cd /usr/share/doc/liblrcalc1
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/liblrcalc1$ ls -la
total 24
drwxr-xr-x 1 root root 4096 Oct  1 09:04 .
drwxr-xr-x 1 root root 4096 Sep 26 17:19 ..
-rw-r--r-- 1 root root  208 Oct  1 09:04 .MEMO
-rw-r--r-- 1 root root  382 Aug  1  2016 changelog.Debian.gz
-rw-r--r-- 1 root root 1258 Aug  1  2016 copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/liblrcalc1$ cat .MEMO
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/sympy/printing/pretty/tests

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/liblrcalc1$ cd /usr/local/lib/python3.8/dist-packages/sympy/printing/pretty/tests
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/printing/pretty/tests$ ls -la
total 204
drwxr-sr-x 1 root   staff    4096 Oct  1 09:04 .
drwxr-sr-x 1 root   staff    4096 Sep 26 17:24 ..
-rw-r--r-- 1 hacker hacker    116 Oct  1 09:04 DISPATCH
-rw-r--r-- 1 root   staff       0 Sep 26 17:24 __init__.py
drwxr-sr-x 2 root   staff    4096 Sep 26 17:24 __pycache__
-rw-r--r-- 1 root   staff  187716 Sep 26 17:24 test_pretty.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/printing/pretty/tests$ cat DISPATCH
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/sympy/physics/quantum/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/printing/pretty/tests$ cd /usr/local/lib/python3.8/dist-packages/sympy/physics/quantum/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/physics/quantum/__pycache__$ ls -la
total 556
drwxr-sr-x 1 root staff  4096 Oct  1 09:04 .
drwxr-sr-x 1 root staff  4096 Sep 26 17:24 ..
-rw-r--r-- 1 root staff    66 Oct  1 09:04 LEAD
-rw-r--r-- 1 root staff  1743 Sep 26 17:24 __init__.cpython-38.pyc
-rw-r--r-- 1 root staff  4674 Sep 26 17:24 anticommutator.cpython-38.pyc
-rw-r--r-- 1 root staff  8703 Sep 26 17:24 boson.cpython-38.pyc
-rw-r--r-- 1 root staff 11893 Sep 26 17:24 cartesian.cpython-38.pyc
-rw-r--r-- 1 root staff 22605 Sep 26 17:24 cg.cpython-38.pyc
-rw-r--r-- 1 root staff 10669 Sep 26 17:24 circuitplot.cpython-38.pyc
-rw-r--r-- 1 root staff 10918 Sep 26 17:24 circuitutils.cpython-38.pyc
-rw-r--r-- 1 root staff  6247 Sep 26 17:24 commutator.cpython-38.pyc
-rw-r--r-- 1 root staff  1764 Sep 26 17:24 constants.cpython-38.pyc
-rw-r--r-- 1 root staff  2942 Sep 26 17:24 dagger.cpython-38.pyc
-rw-r--r-- 1 root staff 10409 Sep 26 17:24 density.cpython-38.pyc
-rw-r--r-- 1 root staff  6199 Sep 26 17:24 fermion.cpython-38.pyc
-rw-r--r-- 1 root staff 35645 Sep 26 17:24 gate.cpython-38.pyc
-rw-r--r-- 1 root staff  9597 Sep 26 17:24 grover.cpython-38.pyc
-rw-r--r-- 1 root staff 19963 Sep 26 17:24 hilbert.cpython-38.pyc
-rw-r--r-- 1 root staff 21748 Sep 26 17:24 identitysearch.cpython-38.pyc
-rw-r--r-- 1 root staff  4252 Sep 26 17:24 innerproduct.cpython-38.pyc
-rw-r--r-- 1 root staff  3666 Sep 26 17:24 matrixcache.cpython-38.pyc
-rw-r--r-- 1 root staff  7379 Sep 26 17:24 matrixutils.cpython-38.pyc
-rw-r--r-- 1 root staff 20159 Sep 26 17:24 operator.cpython-38.pyc
-rw-r--r-- 1 root staff  7056 Sep 26 17:24 operatorordering.cpython-38.pyc
-rw-r--r-- 1 root staff  7804 Sep 26 17:24 operatorset.cpython-38.pyc
-rw-r--r-- 1 root staff 19867 Sep 26 17:24 pauli.cpython-38.pyc
-rw-r--r-- 1 root staff  3168 Sep 26 17:24 piab.cpython-38.pyc
-rw-r--r-- 1 root staff  5066 Sep 26 17:24 qapply.cpython-38.pyc
-rw-r--r-- 1 root staff  8423 Sep 26 17:24 qasm.cpython-38.pyc
-rw-r--r-- 1 root staff 13056 Sep 26 17:24 qexpr.cpython-38.pyc
-rw-r--r-- 1 root staff  7303 Sep 26 17:24 qft.cpython-38.pyc
-rw-r--r-- 1 root staff 22558 Sep 26 17:24 qubit.cpython-38.pyc
-rw-r--r-- 1 root staff 15076 Sep 26 17:24 represent.cpython-38.pyc
-rw-r--r-- 1 root staff 22219 Sep 26 17:24 sho1d.cpython-38.pyc
-rw-r--r-- 1 root staff  5417 Sep 26 17:24 shor.cpython-38.pyc
-rw-r--r-- 1 root staff 75672 Sep 26 17:24 spin.cpython-38.pyc
-rw-r--r-- 1 root staff 31210 Sep 26 17:24 state.cpython-38.pyc
-rw-r--r-- 1 root staff 13797 Sep 26 17:24 tensorproduct.cpython-38.pyc
-rw-r--r-- 1 root staff  5942 Sep 26 17:24 trace.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/physics/quantum/__pycache__$ cat LEAD
Great sleuthing!
The next clue is in: /usr/share/fish/completions
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/sympy/physics/quantum/__pycache__$ cd /usr/share/fish/completions
hacker@commands~an-epic-filesystem-quest:/usr/share/fish/completions$ ls -la
total 4664
drwxr-xr-x 1 root root   4096 Oct  1 09:04 .
drwxr-xr-x 1 root root   4096 Sep 26 17:08 ..
-rw-r--r-- 1 root root     91 Oct  1 09:04 INFO
-rw-r--r-- 1 root root    970 Feb 12  2020 VBoxHeadless.fish
-rw-r--r-- 1 root root   2426 Feb 12  2020 VBoxSDL.fish
-rw-r--r-- 1 root root    206 Feb 12  2020 a2disconf.fish
-rw-r--r-- 1 root root    202 Feb 12  2020 a2dismod.fish
-rw-r--r-- 1 root root    206 Feb 12  2020 a2dissite.fish
-rw-r--r-- 1 root root    136 Feb 12  2020 a2enconf.fish
-rw-r--r-- 1 root root    133 Feb 12  2020 a2enmod.fish
-rw-r--r-- 1 root root    136 Feb 12  2020 a2ensite.fish
-rw-r--r-- 1 root root    444 Feb 12  2020 abbr.fish
-rw-r--r-- 1 root root   1317 Feb 12  2020 abook.fish
-rw-r--r-- 1 root root    110 Feb 12  2020 acat.fish
-rw-r--r-- 1 root root     74 Feb 12  2020 accept.fish
-rw-r--r-- 1 root root   5330 Feb 12  2020 ack.fish
-rw-r--r-- 1 root root   1281 Feb 12  2020 acpi.fish
-rw-r--r-- 1 root root   9525 Feb 12  2020 adb.fish
-rw-r--r-- 1 root root   2578 Feb 12  2020 adduser.fish
-rw-r--r-- 1 root root     27 Feb 12  2020 adiff.fish
-rw-r--r-- 1 root root    108 Feb 12  2020 als.fish
-rw-r--r-- 1 root root   2831 Feb 12  2020 alsactl.fish
-rw-r--r-- 1 root root    441 Feb 12  2020 alsamixer.fish
-rw-r--r-- 1 root root    942 Feb 12  2020 amixer.fish
-rw-r--r-- 1 root root    139 Feb 12  2020 and.fish
-rw-r--r-- 1 root root   5654 Feb 12  2020 animate.fish
-rw-r--r-- 1 root root    355 Feb 12  2020 ansible-galaxy.fish
-rw-r--r-- 1 root root   3656 Feb 12  2020 ansible-playbook.fish
-rw-r--r-- 1 root root   2712 Feb 12  2020 ansible-vault.fish
-rw-r--r-- 1 root root   3273 Feb 12  2020 ansible.fish
-rw-r--r-- 1 root root   4712 Feb 12  2020 ant.fish
-rw-r--r-- 1 root root     27 Feb 12  2020 apack.fish
-rw-r--r-- 1 root root  14884 Feb 12  2020 apm.fish
-rw-r--r-- 1 root root    935 Feb 12  2020 apropos.fish
-rw-r--r-- 1 root root   1799 Feb 12  2020 apt-build.fish
-rw-r--r-- 1 root root   2363 Feb 12  2020 apt-cache.fish
-rw-r--r-- 1 root root    755 Feb 12  2020 apt-cdrom.fish
-rw-r--r-- 1 root root    415 Feb 12  2020 apt-config.fish
-rw-r--r-- 1 root root    284 Feb 12  2020 apt-extracttemplates.fish
-rw-r--r-- 1 root root   1165 Feb 12  2020 apt-file.fish
-rw-r--r-- 1 root root   1113 Feb 12  2020 apt-ftparchive.fish
-rw-r--r-- 1 root root   4336 Feb 12  2020 apt-get.fish
-rw-r--r-- 1 root root    161 Feb 12  2020 apt-key.fish
-rw-r--r-- 1 root root   1826 Feb 12  2020 apt-listbugs.fish
-rw-r--r-- 1 root root    946 Feb 12  2020 apt-listchanges.fish
-rw-r--r-- 1 root root   1721 Feb 12  2020 apt-mark.fish
-rw-r--r-- 1 root root   1372 Feb 12  2020 apt-move.fish
-rw-r--r-- 1 root root    650 Feb 12  2020 apt-proxy-import.fish
-rw-r--r-- 1 root root    954 Feb 12  2020 apt-rdepends.fish
-rw-r--r-- 1 root root    119 Feb 12  2020 apt-setup.fish
-rw-r--r-- 1 root root    738 Feb 12  2020 apt-show-source.fish
-rw-r--r-- 1 root root   1081 Feb 12  2020 apt-show-versions.fish
-rw-r--r-- 1 root root    363 Feb 12  2020 apt-sortpkgs.fish
-rw-r--r-- 1 root root   1014 Feb 12  2020 apt-spy.fish
-rw-r--r-- 1 root root   1485 Feb 12  2020 apt-src.fish
-rw-r--r-- 1 root root    548 Feb 12  2020 apt-zip-inst.fish
-rw-r--r-- 1 root root    839 Feb 12  2020 apt-zip-list.fish
-rw-r--r-- 1 root root   2717 Feb 12  2020 apt.fish
-rw-r--r-- 1 root root   5494 Feb 12  2020 aptitude.fish
-rw-r--r-- 1 root root  22151 Feb 12  2020 arc.fish
-rw-r--r-- 1 root root     29 Feb 12  2020 arepack.fish
-rw-r--r-- 1 root root    729 Feb 12  2020 arp.fish
-rw-r--r-- 1 root root   7098 Feb 12  2020 as.fish
-rw-r--r-- 1 root root   2535 Feb 12  2020 asp.fish
-rw-r--r-- 1 root root    436 Feb 12  2020 at.fish
-rw-r--r-- 1 root root    209 Feb 12  2020 atd.fish
-rw-r--r-- 1 root root   3334 Feb 12  2020 atom.fish
-rw-r--r-- 1 root root   1934 Feb 12  2020 atool.fish
-rw-r--r-- 1 root root    109 Feb 12  2020 atq.fish
-rw-r--r-- 1 root root     61 Feb 12  2020 atrm.fish
-rw-r--r-- 1 root root    116 Feb 12  2020 aunpack.fish
-rw-r--r-- 1 root root  10033 Feb 12  2020 aura.fish
-rw-r--r-- 1 root root    580 Feb 12  2020 awk.fish
-rw-r--r-- 1 root root   6117 Feb 12  2020 aws.fish
-rw-r--r-- 1 root root   1446 Feb 12  2020 badblocks.fish
-rw-r--r-- 1 root root    343 Feb 12  2020 base64.fish
-rw-r--r-- 1 root root   4935 Feb 12  2020 bat.fish
-rw-r--r-- 1 root root     33 Feb 12  2020 bb-wrapper.fish
-rw-r--r-- 1 root root    475 Feb 12  2020 bc.fish
-rw-r--r-- 1 root root    558 Feb 12  2020 bd.fish
-rw-r--r-- 1 root root    142 Feb 12  2020 begin.fish
-rw-r--r-- 1 root root    105 Feb 12  2020 bg.fish
-rw-r--r-- 1 root root   1592 Feb 12  2020 bind.fish
-rw-r--r-- 1 root root   1893 Feb 12  2020 bison.fish
-rw-r--r-- 1 root root    305 Feb 12  2020 block.fish
-rw-r--r-- 1 root root   9838 Feb 12  2020 bosh.fish
-rw-r--r-- 1 root root   2439 Feb 12  2020 bower.fish
-rw-r--r-- 1 root root     59 Feb 12  2020 break.fish
-rw-r--r-- 1 root root    191 Feb 12  2020 brew.fish
-rw-r--r-- 1 root root     47 Feb 12  2020 btdownloadcurses.py.fish
-rw-r--r-- 1 root root     49 Feb 12  2020 btdownloadheadless.py.fish
-rw-r--r-- 1 root root  34469 Feb 12  2020 btrfs.fish
-rw-r--r-- 1 root root    402 Feb 12  2020 builtin.fish
-rw-r--r-- 1 root root  12556 Feb 12  2020 bundle.fish
-rw-r--r-- 1 root root    595 Feb 12  2020 bunzip2.fish
-rw-r--r-- 1 root root   6529 Feb 12  2020 busctl.fish
-rw-r--r-- 1 root root    237 Feb 12  2020 bzcat.fish
-rw-r--r-- 1 root root    878 Feb 12  2020 bzip2.fish
-rw-r--r-- 1 root root    193 Feb 12  2020 bzip2recover.fish
-rw-r--r-- 1 root root   9570 Feb 12  2020 bzr.fish
-rw-r--r-- 1 root root     31 Feb 12  2020 cabal-dev.fish
-rw-r--r-- 1 root root    288 Feb 12  2020 cabal.fish
-rw-r--r-- 1 root root   1636 Feb 12  2020 caddy.fish
-rw-r--r-- 1 root root    794 Feb 12  2020 caffeinate.fish
-rw-r--r-- 1 root root    435 Feb 12  2020 camcontrol.fish
-rw-r--r-- 1 root root    117 Feb 12  2020 cancel.fish
-rw-r--r-- 1 root root   1228 Feb 12  2020 canto.fish
-rw-r--r-- 1 root root   4583 Feb 12  2020 cargo.fish
-rw-r--r-- 1 root root   2276 Feb 12  2020 castnow.fish
-rw-r--r-- 1 root root   1153 Feb 12  2020 cat.fish
-rw-r--r-- 1 root root     96 Feb 12  2020 cd.fish
-rw-r--r-- 1 root root    753 Feb 12  2020 cdh.fish
-rw-r--r-- 1 root root   8562 Feb 12  2020 cdrecord.fish
-rw-r--r-- 1 root root  25447 Feb 12  2020 cf.fish
-rw-r--r-- 1 root root    705 Feb 12  2020 chgrp.fish
-rw-r--r-- 1 root root    875 Feb 12  2020 chmod.fish
-rw-r--r-- 1 root root    812 Feb 12  2020 chown.fish
-rw-r--r-- 1 root root   7474 Feb 12  2020 chronyc.fish
-rw-r--r-- 1 root root    746 Feb 12  2020 chsh.fish
-rw-r--r-- 1 root root    592 Feb 12  2020 clang++.fish
-rw-r--r-- 1 root root    964 Feb 12  2020 clang.fish
-rw-r--r-- 1 root root   5652 Feb 12  2020 climate.fish
-rw-r--r-- 1 root root   2830 Feb 12  2020 code.fish
-rw-r--r-- 1 root root     30 Feb 12  2020 colordiff.fish
-rw-r--r-- 1 root root     29 Feb 12  2020 colorsvn.fish
-rw-r--r-- 1 root root    463 Feb 12  2020 combine.fish
-rw-r--r-- 1 root root    652 Feb 12  2020 command.fish
-rw-r--r-- 1 root root   1413 Feb 12  2020 commandline.fish
-rw-r--r-- 1 root root   4156 Feb 12  2020 compare.fish
-rw-r--r-- 1 root root   1411 Feb 12  2020 complete.fish
-rw-r--r-- 1 root root  31996 Feb 12  2020 composer.fish
-rw-r--r-- 1 root root     43 Feb 12  2020 composer.phar.fish
-rw-r--r-- 1 root root   7519 Feb 12  2020 composite.fish
-rw-r--r-- 1 root root  12075 Feb 12  2020 conda.fish
-rw-r--r-- 1 root root   4400 Feb 12  2020 configure.fish
-rw-r--r-- 1 root root    780 Feb 12  2020 conjure.fish
-rw-r--r-- 1 root root   4790 Feb 12  2020 connmanctl.fish
-rw-r--r-- 1 root root     63 Feb 12  2020 continue.fish
-rw-r--r-- 1 root root  20219 Feb 12  2020 convert.fish
-rw-r--r-- 1 root root    696 Feb 12  2020 cowsay.fish
-rw-r--r-- 1 root root    728 Feb 12  2020 cowthink.fish
-rw-r--r-- 1 root root   4284 Feb 12  2020 cp.fish
-rw-r--r-- 1 root root   7599 Feb 12  2020 cryptsetup.fish
-rw-r--r-- 1 root root   9202 Feb 12  2020 csc.fish
-rw-r--r-- 1 root root    607 Feb 12  2020 csi.fish
-rw-r--r-- 1 root root     82 Feb 12  2020 cupsaccept.fish
-rw-r--r-- 1 root root    316 Feb 12  2020 cupsdisable.fish
-rw-r--r-- 1 root root    310 Feb 12  2020 cupsenable.fish
-rw-r--r-- 1 root root     82 Feb 12  2020 cupsreject.fish
-rw-r--r-- 1 root root  21164 Feb 12  2020 curl.fish
-rw-r--r-- 1 root root    732 Feb 12  2020 cut.fish
-rw-r--r-- 1 root root  33049 Feb 12  2020 cvs.fish
-rw-r--r-- 1 root root   4867 Feb 12  2020 cwebp.fish
-rw-r--r-- 1 root root   2314 Feb 12  2020 cygpath.fish
-rw-r--r-- 1 root root   2526 Feb 12  2020 cygport.fish
-rw-r--r-- 1 root root   1836 Feb 12  2020 cygstart.fish
-rw-r--r-- 1 root root  95738 Feb 12  2020 darcs.fish
-rw-r--r-- 1 root root   1974 Feb 12  2020 date.fish
-rw-r--r-- 1 root root   2530 Feb 12  2020 dconf.fish
-rw-r--r-- 1 root root   5022 Feb 12  2020 dd.fish
-rw-r--r-- 1 root root   2580 Feb 12  2020 defaults.fish
-rw-r--r-- 1 root root   1549 Feb 12  2020 df.fish
-rw-r--r-- 1 root root   2967 Feb 12  2020 dhcpcd.fish
-rw-r--r-- 1 root root   1884 Feb 12  2020 diff.fish
-rw-r--r-- 1 root root   3988 Feb 12  2020 dig.fish
-rw-r--r-- 1 root root  13699 Feb 12  2020 diskutil.fish
-rw-r--r-- 1 root root   8197 Feb 12  2020 display.fish
-rw-r--r-- 1 root root     60 Feb 12  2020 djview.fish
-rw-r--r-- 1 root root     61 Feb 12  2020 djview4.fish
-rw-r--r-- 1 root root    347 Feb 12  2020 dlocate.fish
-rw-r--r-- 1 root root   2537 Feb 12  2020 dmesg.fish
-rw-r--r-- 1 root root  22135 Feb 12  2020 dnf.fish
-rw-r--r-- 1 root root   1714 Feb 12  2020 doas.fish
-rw-r--r-- 1 root root    102 Feb 12  2020 docker.fish
-rw-r--r-- 1 root root    898 Feb 12  2020 dpkg-reconfigure.fish
-rw-r--r-- 1 root root   1374 Feb 12  2020 dpkg.fish
-rw-r--r-- 1 root root   1197 Feb 12  2020 du.fish
-rw-r--r-- 1 root root   1454 Mar  7  2020 dupload.fish
-rw-r--r-- 1 root root   3135 Feb 12  2020 duply.fish
-rw-r--r-- 1 root root     73 Feb 12  2020 dvipdf.fish
-rw-r--r-- 1 root root     72 Feb 12  2020 dvipdfm.fish
-rw-r--r-- 1 root root   2531 Feb 12  2020 ebuild.fish
-rw-r--r-- 1 root root    278 Feb 12  2020 echo.fish
-rw-r--r-- 1 root root     26 Feb 12  2020 egrep.fish
-rw-r--r-- 1 root root   1641 Feb 12  2020 eix-sync.fish
-rw-r--r-- 1 root root   3166 Feb 12  2020 eix.fish
-rw-r--r-- 1 root root     27 Feb 12  2020 elatex.fish
-rw-r--r-- 1 root root   1083 Feb 12  2020 elixir.fish
-rw-r--r-- 1 root root   3982 Feb 12  2020 emacs.fish
-rw-r--r-- 1 root root   2697 Feb 12  2020 emaint.fish
-rw-r--r-- 1 root root   6554 Feb 12  2020 emerge.fish
-rw-r--r-- 1 root root   1049 Feb 12  2020 encfs.fish
-rw-r--r-- 1 root root    356 Feb 12  2020 entr.fish
-rw-r--r-- 1 root root   1404 Feb 12  2020 env.fish
-rw-r--r-- 1 root root   8610 Feb 12  2020 eopkg.fish
-rw-r--r-- 1 root root    789 Feb 12  2020 epkginfo.fish
-rw-r--r-- 1 root root   9237 Feb 12  2020 equery.fish
-rw-r--r-- 1 root root   2700 Feb 12  2020 eselect.fish
-rw-r--r-- 1 root root     24 Feb 12  2020 etex.fish
-rw-r--r-- 1 root root     58 Feb 12  2020 eval.fish
-rw-r--r-- 1 root root    791 Feb 12  2020 evince.fish
-rw-r--r-- 1 root root    152 Feb 12  2020 exec.fish
-rw-r--r-- 1 root root   2327 Feb 12  2020 exercism.fish
-rw-r--r-- 1 root root    178 Feb 12  2020 exit.fish
-rw-r--r-- 1 root root    379 Feb 12  2020 expand.fish
-rw-r--r-- 1 root root   3045 Feb 12  2020 ezjail-admin.fish
-rw-r--r-- 1 root root   4140 Feb 12  2020 fab.fish
-rw-r--r-- 1 root root   6341 Feb 12  2020 feh.fish
-rw-r--r-- 1 root root   6558 Feb 12  2020 ffmpeg.fish
-rw-r--r-- 1 root root   3529 Feb 12  2020 ffplay.fish
-rw-r--r-- 1 root root   4760 Feb 12  2020 ffprobe.fish
-rw-r--r-- 1 root root    105 Feb 12  2020 fg.fish
-rw-r--r-- 1 root root     26 Feb 12  2020 fgrep.fish
-rw-r--r-- 1 root root   1805 Feb 12  2020 figlet.fish
-rw-r--r-- 1 root root   1522 Feb 12  2020 file.fish
-rw-r--r-- 1 root root   6100 Feb 12  2020 find.fish
-rw-r--r-- 1 root root   1739 Feb 12  2020 fish.fish
-rw-r--r-- 1 root root    751 Feb 12  2020 fish_indent.fish
-rw-r--r-- 1 root root   5965 Feb 12  2020 flac.fish
-rw-r--r-- 1 root root   4172 Feb 12  2020 flatpak.fish
-rw-r--r-- 1 root root     58 Feb 12  2020 fluxbox-remote.fish
-rw-r--r-- 1 root root    227 Feb 12  2020 for.fish
-rw-r--r-- 1 root root  31977 Feb 12  2020 fossil.fish
-rw-r--r-- 1 root root   6132 Feb 12  2020 fsharpc.fish
-rw-r--r-- 1 root root   4323 Feb 12  2020 fsharpi.fish
-rw-r--r-- 1 root root     24 Feb 12  2020 ftp.fish
-rw-r--r-- 1 root root    233 Feb 12  2020 funced.fish
-rw-r--r-- 1 root root     62 Feb 12  2020 funcsave.fish
-rw-r--r-- 1 root root    952 Feb 12  2020 function.fish
-rw-r--r-- 1 root root   1192 Feb 12  2020 functions.fish
-rw-r--r-- 1 root root   1282 Feb 12  2020 fuser.fish
-rw-r--r-- 1 root root    443 Feb 12  2020 fusermount.fish
-rw-r--r-- 1 root root   4610 Feb 12  2020 fzf.fish
-rw-r--r-- 1 root root     23 Feb 12  2020 g++.fish
-rw-r--r-- 1 root root 166397 Feb 12  2020 gcc.fish
-rw-r--r-- 1 root root   1812 Feb 12  2020 gdb.fish
-rw-r--r-- 1 root root  11825 Feb 12  2020 gem.fish
-rw-r--r-- 1 root root 138715 Feb 12  2020 git.fish
-rw-r--r-- 1 root root  11391 Feb 12  2020 go.fish
-rw-r--r-- 1 root root   1948 Feb 12  2020 godoc.fish
-rw-r--r-- 1 root root    561 Feb 12  2020 gofmt.fish
-rw-r--r-- 1 root root    440 Feb 12  2020 goimports.fish
-rw-r--r-- 1 root root    269 Feb 12  2020 golint.fish
-rw-r--r-- 1 root root    703 Feb 12  2020 gorename.fish
-rw-r--r-- 1 root root    709 Feb 12  2020 gpasswd.fish
-rw-r--r-- 1 root root     24 Feb 12  2020 gpg.fish
-rw-r--r-- 1 root root     25 Feb 12  2020 gpg1.fish
-rw-r--r-- 1 root root     25 Feb 12  2020 gpg2.fish
-rw-r--r-- 1 root root   5208 Feb 12  2020 gphoto2.fish
-rw-r--r-- 1 root root   2262 Feb 12  2020 gprof.fish
-rw-r--r-- 1 root root   3453 Feb 12  2020 gradle.fish
-rw-r--r-- 1 root root   3483 Feb 12  2020 grep.fish
-rw-r--r-- 1 root root    599 Feb 12  2020 groupadd.fish
-rw-r--r-- 1 root root   2810 Feb 12  2020 grub-file.fish
-rw-r--r-- 1 root root   2952 Feb 12  2020 grub-install.fish
-rw-r--r-- 1 root root   2078 Feb 12  2020 grub-mkrescue.fish
-rw-r--r-- 1 root root   1477 Feb 12  2020 grunt.fish
-rw-r--r-- 1 root root   4451 Feb 12  2020 gsettings.fish
-rw-r--r-- 1 root root    855 Feb 12  2020 gunzip.fish
-rw-r--r-- 1 root root   3569 Feb 12  2020 gv.fish
-rw-r--r-- 1 root root     25 Feb 12  2020 gvim.fish
-rw-r--r-- 1 root root     28 Feb 12  2020 gvimdiff.fish
-rw-r--r-- 1 root root    964 Feb 12  2020 gzip.fish
-rw-r--r-- 1 root root    679 Feb 12  2020 head.fish
-rw-r--r-- 1 root root  14880 Feb 12  2020 helm.fish
-rw-r--r-- 1 root root   6115 Feb 12  2020 help.fish
-rw-r--r-- 1 root root  11733 Feb 12  2020 heroku.fish
-rw-r--r-- 1 root root  94915 Feb 12  2020 hg.fish
-rw-r--r-- 1 root root    641 Feb 12  2020 highlight.fish
-rw-r--r-- 1 root root   1730 Feb 12  2020 history.fish
-rw-r--r-- 1 root root   1126 Feb 12  2020 hjson.fish
-rw-r--r-- 1 root root  16004 Feb 12  2020 hledger.fish
-rw-r--r-- 1 root root    639 Feb 12  2020 htop.fish
-rw-r--r-- 1 root root  15142 Feb 12  2020 hugo.fish
-rw-r--r-- 1 root root   1279 Feb 12  2020 hwinfo.fish
-rw-r--r-- 1 root root    677 Feb 12  2020 i3-msg.fish
-rw-r--r-- 1 root root    500 Feb 12  2020 iconv.fish
-rw-r--r-- 1 root root    396 Feb 12  2020 id.fish
-rw-r--r-- 1 root root   2892 Feb 12  2020 identify.fish
-rw-r--r-- 1 root root   1161 Feb 12  2020 iex.fish
-rw-r--r-- 1 root root    136 Feb 12  2020 if.fish
-rw-r--r-- 1 root root    397 Feb 12  2020 ifconfig.fish
-rw-r--r-- 1 root root   1677 Feb 12  2020 ifdata.fish
-rw-r--r-- 1 root root    115 Feb 12  2020 ifdown.fish
-rw-r--r-- 1 root root    111 Feb 12  2020 ifup.fish
-rw-r--r-- 1 root root   5822 Feb 12  2020 import.fish
-rw-r--r-- 1 root root   1075 Feb 12  2020 invoke-rc.d.fish
-rw-r--r-- 1 root root  18292 Feb 12  2020 ip.fish
-rw-r--r-- 1 root root   2063 Feb 12  2020 ipset.fish
-rw-r--r-- 1 root root   6529 Feb 12  2020 iptables.fish
-rw-r--r-- 1 root root   1818 Feb 12  2020 irb.fish
-rw-r--r-- 1 root root  12144 Feb 12  2020 iw.fish
-rw-r--r-- 1 root root    420 Feb 12  2020 j.fish
-rw-r--r-- 1 root root    450 Feb 12  2020 jbake.fish
-rw-r--r-- 1 root root   7030 Feb 12  2020 jest.fish
-rw-r--r-- 1 root root   2888 Feb 12  2020 jhipster.fish
-rw-r--r-- 1 root root    343 Feb 12  2020 jobs.fish
-rw-r--r-- 1 root root   3742 Feb 12  2020 journalctl.fish
-rw-r--r-- 1 root root   1762 Feb 12  2020 jq.fish
-rw-r--r-- 1 root root   1168 Feb 12  2020 kak.fish
-rw-r--r-- 1 root root    737 Feb 12  2020 kcmshell5.fish
-rw-r--r-- 1 root root   2134 Feb 12  2020 kdeconnect-cli.fish
-rw-r--r-- 1 root root   6477 Feb 12  2020 keepassxc-cli.fish
-rw-r--r-- 1 root root   9197 Feb 12  2020 keybase.fish
-rw-r--r-- 1 root root    955 Feb 12  2020 kill.fish
-rw-r--r-- 1 root root   2516 Feb 12  2020 killall.fish
-rw-r--r-- 1 root root  11840 Feb 12  2020 kitchen.fish
-rw-r--r-- 1 root root    179 Feb 12  2020 kitty.fish
-rw-r--r-- 1 root root   1510 Feb 12  2020 kldload.fish
-rw-r--r-- 1 root root    377 Feb 12  2020 kldunload.fish
-rw-r--r-- 1 root root     21 Feb 12  2020 la.fish
-rw-r--r-- 1 root root     26 Feb 12  2020 latex.fish
-rw-r--r-- 1 root root   5202 Feb 12  2020 latexmk.fish
-rw-r--r-- 1 root root   5644 Feb 12  2020 launchctl.fish
-rw-r--r-- 1 root root   3284 Feb 12  2020 lein.fish
-rw-r--r-- 1 root root   3750 Feb 12  2020 less.fish
-rw-r--r-- 1 root root   1223 Feb 12  2020 light.fish
-rw-r--r-- 1 root root     21 Feb 12  2020 ll.fish
-rw-r--r-- 1 root root   1241 Feb 12  2020 ln.fish
-rw-r--r-- 1 root root   2429 Feb 12  2020 localectl.fish
-rw-r--r-- 1 root root   1281 Feb 12  2020 locate.fish
-rw-r--r-- 1 root root   2094 Feb 12  2020 loginctl.fish
-rw-r--r-- 1 root root    831 Feb 12  2020 logkeys.fish
-rw-r--r-- 1 root root    723 Feb 12  2020 lp.fish
-rw-r--r-- 1 root root   3845 Feb 12  2020 lpadmin.fish
-rw-r--r-- 1 root root    970 Feb 12  2020 lpinfo.fish
-rw-r--r-- 1 root root     28 Feb 12  2020 lpmove.fish
-rw-r--r-- 1 root root    710 Feb 12  2020 lpoptions.fish
-rw-r--r-- 1 root root    288 Feb 12  2020 lppasswd.fish
-rw-r--r-- 1 root root     99 Feb 12  2020 lpq.fish
-rw-r--r-- 1 root root    976 Feb 12  2020 lpr.fish
-rw-r--r-- 1 root root     25 Feb 12  2020 lprm.fish
-rw-r--r-- 1 root root   1351 Feb 12  2020 lpstat.fish
-rw-r--r-- 1 root root   9674 Feb 12  2020 ls.fish
-rw-r--r-- 1 root root   1221 Feb 12  2020 lsblk.fish
-rw-r--r-- 1 root root   1222 Feb 12  2020 lscpu.fish
-rw-r--r-- 1 root root   1352 Feb 12  2020 lsof.fish
-rw-r--r-- 1 root root    684 Feb 12  2020 lsusb.fish
-rw-r--r-- 1 root root    558 Feb 12  2020 lua.fish
-rw-r--r-- 1 root root     29 Feb 12  2020 lualatex.fish
-rw-r--r-- 1 root root   1770 Feb 12  2020 lunchy.fish
-rw-r--r-- 1 root root   4541 Feb 12  2020 lxc.fish
-rw-r--r-- 1 root root    345 Feb 12  2020 lxpanel.fish
-rw-r--r-- 1 root root   1800 Feb 12  2020 lz4.fish
-rw-r--r-- 1 root root     48 Feb 12  2020 lz4c.fish
-rw-r--r-- 1 root root    642 Feb 12  2020 lz4cat.fish
-rw-r--r-- 1 root root   1710 Feb 12  2020 m4.fish
-rw-r--r-- 1 root root   9527 Feb 12  2020 machinectl.fish
-rw-r--r-- 1 root root  35095 Feb 12  2020 magento.fish
-rw-r--r-- 1 root root   3041 Feb 12  2020 make.fish
-rw-r--r-- 1 root root    672 Feb 12  2020 makedepend.fish
-rw-r--r-- 1 root root   1710 Feb 12  2020 makensis.fish
-rw-r--r-- 1 root root   2869 Feb 12  2020 makepkg.fish
-rw-r--r-- 1 root root   1865 Feb 12  2020 man.fish
-rw-r--r-- 1 root root   3286 Feb 12  2020 mariner.fish
-rw-r--r-- 1 root root     63 Feb 12  2020 math.fish
-rw-r--r-- 1 root root   1551 Feb 12  2020 mc.fish
-rw-r--r-- 1 root root    706 Feb 12  2020 md5sum.fish
-rw-r--r-- 1 root root  18374 Feb 12  2020 mdadm.fish
-rw-r--r-- 1 root root   1262 Feb 12  2020 mdbook.fish
-rw-r--r-- 1 root root    718 Feb 12  2020 mddiagnose.fish
-rw-r--r-- 1 root root    831 Feb 12  2020 mdfind.fish
-rw-r--r-- 1 root root    936 Feb 12  2020 mdimport.fish
-rw-r--r-- 1 root root    406 Feb 12  2020 mdls.fish
-rw-r--r-- 1 root root   1108 Feb 12  2020 mdutil.fish
-rw-r--r-- 1 root root   2394 Feb 12  2020 meson.fish
-rw-r--r-- 1 root root  10388 Feb 12  2020 minikube.fish
-rw-r--r-- 1 root root   9114 Feb 12  2020 mix.fish
-rw-r--r-- 1 root root    829 Feb 12  2020 mkdir.fish
-rw-r--r-- 1 root root   3807 Feb 12  2020 mkdocs.fish
-rw-r--r-- 1 root root   2083 Feb 12  2020 mkdosfs.fish
-rw-r--r-- 1 root root     32 Feb 12  2020 mkfs.fat.fish
-rw-r--r-- 1 root root     33 Feb 12  2020 mkfs.vfat.fish
-rw-r--r-- 1 root root   2142 Feb 12  2020 mkinitcpio.fish
-rw-r--r-- 1 root root    931 Feb 12  2020 mktemp.fish
-rw-r--r-- 1 root root   6410 Feb 12  2020 mkvextract.fish
-rw-r--r-- 1 root root   3540 Feb 12  2020 mocha.fish
-rw-r--r-- 1 root root   2777 Feb 12  2020 mocp.fish
-rw-r--r-- 1 root root    843 Feb 12  2020 modinfo.fish
-rw-r--r-- 1 root root   1730 Feb 12  2020 modprobe.fish
-rw-r--r-- 1 root root  18378 Feb 12  2020 mogrify.fish
-rw-r--r-- 1 root root   9144 Feb 12  2020 montage.fish
-rw-r--r-- 1 root root    895 Feb 12  2020 mosh.fish
-rw-r--r-- 1 root root   1857 Feb 12  2020 mount.fish
-rw-r--r-- 1 root root   3201 Feb 12  2020 mplayer.fish
-rw-r--r-- 1 root root   2461 Feb 12  2020 msgfmt.fish
-rw-r--r-- 1 root root     57 Feb 12  2020 mupdf.fish
-rw-r--r-- 1 root root   2032 Feb 12  2020 mutt.fish
-rw-r--r-- 1 root root   2659 Feb 12  2020 mv.fish
-rw-r--r-- 1 root root 132992 Feb 12  2020 mvn.fish
-rw-r--r-- 1 root root    579 Feb 12  2020 namei.fish
-rw-r--r-- 1 root root    235 Feb 12  2020 native2ascii.fish
-rw-r--r-- 1 root root   1241 Feb 12  2020 nc.fish
-rw-r--r-- 1 root root    349 Feb 12  2020 ncdu.fish
-rw-r--r-- 1 root root   3681 Feb 12  2020 netctl-auto.fish
-rw-r--r-- 1 root root   2002 Feb 12  2020 netctl.fish
-rw-r--r-- 1 root root   1218 Feb 12  2020 nethack.fish
-rw-r--r-- 1 root root    303 Feb 12  2020 networkctl.fish
-rw-r--r-- 1 root root     57 Feb 12  2020 nextd.fish
-rw-r--r-- 1 root root   2472 Feb 12  2020 ngrok.fish
-rw-r--r-- 1 root root    355 Feb 12  2020 nice.fish
-rw-r--r-- 1 root root   1401 Feb 12  2020 ninja.fish
-rw-r--r-- 1 root root   1470 Feb 12  2020 nl.fish
-rw-r--r-- 1 root root   2079 Feb 12  2020 nm.fish
-rw-r--r-- 1 root root   9939 Feb 12  2020 nmcli.fish
-rw-r--r-- 1 root root  20291 Feb 12  2020 node.fish
-rw-r--r-- 1 root root    138 Feb 12  2020 not.fish
-rw-r--r-- 1 root root  11690 Feb 12  2020 npm.fish
-rw-r--r-- 1 root root     24 Feb 12  2020 nvim.fish
-rw-r--r-- 1 root root    529 Feb 12  2020 nvram.fish
-rw-r--r-- 1 root root   4788 Feb 12  2020 objdump.fish
-rw-r--r-- 1 root root  12643 Feb 12  2020 obnam.fish
-rw-r--r-- 1 root root   2290 Feb 12  2020 oggenc.fish
-rw-r--r-- 1 root root     26 Feb 12  2020 omega.fish
-rw-r--r-- 1 root root   8205 Feb 12  2020 opam.fish
-rw-r--r-- 1 root root   1438 Feb 12  2020 open.fish
-rw-r--r-- 1 root root   1528 Feb 12  2020 openocd.fish
-rw-r--r-- 1 root root   5866 Feb 12  2020 opkg.fish
-rw-r--r-- 1 root root   3228 Feb 12  2020 optipng.fish
-rw-r--r-- 1 root root    137 Feb 12  2020 or.fish
-rw-r--r-- 1 root root  45271 Feb 12  2020 p4.fish
-rw-r--r-- 1 root root  11087 Feb 12  2020 pacaur.fish
-rw-r--r-- 1 root root     35 Feb 12  2020 pacman-color.fish
-rw-r--r-- 1 root root   1644 Feb 12  2020 pacman-key.fish
-rw-r--r-- 1 root root   9355 Feb 12  2020 pacman.fish
-rw-r--r-- 1 root root     31 Feb 12  2020 pacmatic.fish
-rw-r--r-- 1 root root   1274 Feb 12  2020 pacmd.fish
-rw-r--r-- 1 root root   7078 Feb 12  2020 pactl.fish
-rw-r--r-- 1 root root    827 Feb 12  2020 pactree.fish
-rw-r--r-- 1 root root   6738 Feb 12  2020 pandoc.fish
-rw-r--r-- 1 root root   2708 Feb 12  2020 passwd.fish
-rw-r--r-- 1 root root   3323 Feb 12  2020 patch.fish
-rw-r--r-- 1 root root   1201 Feb 12  2020 patool.fish
-rw-r--r-- 1 root root    458 Feb 12  2020 pbget.fish
-rw-r--r-- 1 root root     31 Feb 12  2020 pdfelatex.fish
-rw-r--r-- 1 root root     29 Feb 12  2020 pdfetex.fish
-rw-r--r-- 1 root root     29 Feb 12  2020 pdflatex.fish
-rw-r--r-- 1 root root     28 Feb 12  2020 pdftex.fish
-rw-r--r-- 1 root root   1356 Feb 12  2020 pdftotext.fish
-rw-r--r-- 1 root root   3454 Feb 12  2020 perl.fish
-rw-r--r-- 1 root root   1389 Feb 12  2020 pfctl.fish
-rw-r--r-- 1 root root     25 Feb 12  2020 pftp.fish
-rw-r--r-- 1 root root    153 Feb 12  2020 pgrep.fish
-rw-r--r-- 1 root root   7389 Feb 12  2020 phpunit.fish
-rw-r--r-- 1 root root   1023 Feb 12  2020 pine.fish
-rw-r--r-- 1 root root   2014 Feb 12  2020 ping.fish
-rw-r--r-- 1 root root    884 Feb 12  2020 pinky.fish
-rw-r--r-- 1 root root     71 Feb 12  2020 pip.fish
-rw-r--r-- 1 root root    409 Feb 12  2020 pip2.fish
-rw-r--r-- 1 root root    409 Feb 12  2020 pip3.fish
-rw-r--r-- 1 root root    227 Feb 12  2020 pipenv.fish
-rw-r--r-- 1 root root   2457 Feb 12  2020 pkg-config.fish
-rw-r--r-- 1 root root   7574 Feb 12  2020 pkg.fish
-rw-r--r-- 1 root root    460 Feb 12  2020 pkg_add.fish
-rw-r--r-- 1 root root    206 Feb 12  2020 pkg_delete.fish
-rw-r--r-- 1 root root    102 Feb 12  2020 pkg_info.fish
-rw-r--r-- 1 root root    312 Feb 12  2020 pkgadd.fish
-rw-r--r-- 1 root root   1110 Feb 12  2020 pkgfile.fish
-rw-r--r-- 1 root root    556 Feb 12  2020 pkginfo.fish
-rw-r--r-- 1 root root   1164 Feb 12  2020 pkgmk.fish
-rw-r--r-- 1 root root    268 Feb 12  2020 pkgrm.fish
-rw-r--r-- 1 root root    202 Feb 12  2020 pkill.fish
-rw-r--r-- 1 root root   1292 Feb 12  2020 plutil.fish
-rw-r--r-- 1 root root    516 Feb 12  2020 poff.fish
-rw-r--r-- 1 root root     69 Feb 12  2020 pon.fish
-rw-r--r-- 1 root root   9650 Feb 12  2020 port.fish
-rw-r--r-- 1 root root   4210 Feb 12  2020 portmaster.fish
-rw-r--r-- 1 root root    423 Feb 12  2020 ports.fish
-rw-r--r-- 1 root root    488 Feb 12  2020 poweroff.fish
-rw-r--r-- 1 root root     32 Feb 12  2020 powerpill.fish
-rw-r--r-- 1 root root     57 Feb 12  2020 prevd.fish
-rw-r--r-- 1 root root  11767 Feb 12  2020 prt-get.fish
-rw-r--r-- 1 root root   2571 Feb 12  2020 ps.fish
-rw-r--r-- 1 root root     72 Feb 12  2020 ps2pdf.fish
-rw-r--r-- 1 root root   2906 Feb 12  2020 psql.fish
-rw-r--r-- 1 root root     48 Feb 12  2020 pstack.fish
-rw-r--r-- 1 root root    276 Feb 12  2020 psub.fish
-rw-r--r-- 1 root root   1138 Feb 12  2020 pushd.fish
-rw-r--r-- 1 root root   2349 Feb 12  2020 pv.fish
-rw-r--r-- 1 root root   1294 Feb 12  2020 pydf.fish
-rw-r--r-- 1 root root   1554 Feb 12  2020 pygmentize.fish
-rw-r--r-- 1 root root   2339 Feb 12  2020 python.fish
-rw-r--r-- 1 root root   1610 Feb 12  2020 python2.fish
-rw-r--r-- 1 root root   1667 Feb 12  2020 python3.fish
-rw-r--r-- 1 root root   1101 Feb 12  2020 pzstd.fish
-rw-r--r-- 1 root root   7727 Feb 12  2020 qubes-gpg-client.fish
-rw-r--r-- 1 root root   3262 Feb 12  2020 quilt.fish
-rw-r--r-- 1 root root     60 Feb 12  2020 random.fish
-rw-r--r-- 1 root root   1017 Feb 12  2020 ranger.fish
-rw-r--r-- 1 root root   4064 Feb 12  2020 rbenv.fish
-rw-r--r-- 1 root root   1080 Feb 12  2020 rc-service.fish
-rw-r--r-- 1 root root   1288 Feb 12  2020 rc-update.fish
-rw-r--r-- 1 root root    340 Feb 12  2020 rcctl.fish
-rw-r--r-- 1 root root   1334 Feb 12  2020 read.fish
-rw-r--r-- 1 root root    673 Feb 12  2020 readlink.fish
-rw-r--r-- 1 root root    896 Feb 12  2020 realpath.fish
-rw-r--r-- 1 root root     74 Feb 12  2020 reject.fish
-rw-r--r-- 1 root root    197 Feb 12  2020 rejmerge.fish
-rw-r--r-- 1 root root    274 Feb 12  2020 renice.fish
-rw-r--r-- 1 root root   1750 Feb 12  2020 resolvectl.fish
-rw-r--r-- 1 root root    216 Feb 12  2020 return.fish
-rw-r--r-- 1 root root    351 Feb 12  2020 rfkill.fish
-rw-r--r-- 1 root root     26 Feb 12  2020 rgrep.fish
-rw-r--r-- 1 root root   1552 Feb 12  2020 rm.fish
-rw-r--r-- 1 root root    423 Feb 12  2020 rmdir.fish
-rw-r--r-- 1 root root    562 Feb 12  2020 rmmod.fish
-rw-r--r-- 1 root root    511 Feb 12  2020 root.fish
-rw-r--r-- 1 root root   9905 Feb 12  2020 rpm.fish
-rw-r--r-- 1 root root   9042 Feb 12  2020 rsync.fish
-rw-r--r-- 1 root root    814 Feb 12  2020 ruby-build.fish
-rw-r--r-- 1 root root   1192 Feb 12  2020 ruby.fish
-rw-r--r-- 1 root root   2843 Feb 12  2020 rustc.fish
-rw-r--r-- 1 root root  11245 Feb 12  2020 rustup.fish
-rw-r--r-- 1 root root  12688 Feb 12  2020 s3cmd.fish
-rw-r--r-- 1 root root   4076 Feb 12  2020 sass-convert.fish
-rw-r--r-- 1 root root   6231 Feb 12  2020 sass.fish
-rw-r--r-- 1 root root   3982 Feb 12  2020 sbt.fish
-rw-r--r-- 1 root root   2896 Feb 12  2020 scanimage.fish
-rw-r--r-- 1 root root   5053 Feb 12  2020 scons.fish
-rw-r--r-- 1 root root   2193 Feb 12  2020 scp.fish
-rw-r--r-- 1 root root   3608 Feb 12  2020 screen.fish
-rw-r--r-- 1 root root    742 Feb 12  2020 scrot.fish
-rw-r--r-- 1 root root   6228 Feb 12  2020 scss.fish
-rw-r--r-- 1 root root   1306 Feb 12  2020 sed.fish
-rw-r--r-- 1 root root    676 Feb 12  2020 seq.fish
-rw-r--r-- 1 root root    585 Feb 12  2020 serve.fish
-rw-r--r-- 1 root root   1469 Feb 12  2020 service.fish
-rw-r--r-- 1 root root   6374 Feb 12  2020 set.fish
-rw-r--r-- 1 root root    602 Feb 12  2020 set_color.fish
-rw-r--r-- 1 root root   2409 Feb 12  2020 setfacl.fish
-rw-r--r-- 1 root root    616 Feb 12  2020 setsid.fish
-rw-r--r-- 1 root root   2360 Feb 12  2020 setxkbmap.fish
-rw-r--r-- 1 root root 118296 Feb 12  2020 sfdx.fish
-rw-r--r-- 1 root root     30 Feb 12  2020 sha1sum.fish
-rw-r--r-- 1 root root     32 Feb 12  2020 sha224sum.fish
-rw-r--r-- 1 root root     32 Feb 12  2020 sha256sum.fish
-rw-r--r-- 1 root root     32 Feb 12  2020 sha384sum.fish
-rw-r--r-- 1 root root     32 Feb 12  2020 sha512sum.fish
-rw-r--r-- 1 root root    405 Feb 12  2020 signify.fish
-rw-r--r-- 1 root root  12054 Feb 12  2020 snap.fish
-rw-r--r-- 1 root root   1501 Feb 12  2020 sort.fish
-rw-r--r-- 1 root root   1668 Feb 12  2020 speedtest-cli.fish
-rw-r--r-- 1 root root     39 Feb 12  2020 speedtest.fish
-rw-r--r-- 1 root root   5724 Feb 12  2020 src.fish
-rw-r--r-- 1 root root   2161 Feb 12  2020 ssh.fish
-rw-r--r-- 1 root root    646 Feb 12  2020 sshfs.fish
-rw-r--r-- 1 root root   5684 Feb 12  2020 stack.fish
-rw-r--r-- 1 root root   1499 Feb 12  2020 stat.fish
-rw-r--r-- 1 root root   4453 Feb 12  2020 status.fish
-rw-r--r-- 1 root root   2900 Feb 12  2020 stream.fish
-rw-r--r-- 1 root root   5254 Feb 12  2020 string.fish
-rw-r--r-- 1 root root    551 Feb 12  2020 su.fish
-rw-r--r-- 1 root root   1847 Feb 12  2020 subl.fish
-rw-r--r-- 1 root root   3748 Feb 12  2020 sudo.fish
-rw-r--r-- 1 root root  15711 Feb 12  2020 svn.fish
-rw-r--r-- 1 root root    878 Feb 12  2020 sylpheed.fish
-rw-r--r-- 1 root root   9905 Feb 12  2020 sysbench.fish
-rw-r--r-- 1 root root   2497 Feb 12  2020 sysctl.fish
-rw-r--r-- 1 root root   6650 Feb 12  2020 systemctl.fish
-rw-r--r-- 1 root root   2077 Feb 12  2020 systemd-analyze.fish
-rw-r--r-- 1 root root   3937 Feb 12  2020 systemd-nspawn.fish
-rw-r--r-- 1 root root   1996 Feb 12  2020 tail.fish
-rw-r--r-- 1 root root   4786 Feb 12  2020 tar.fish
-rw-r--r-- 1 root root    276 Feb 12  2020 tee.fish
-rw-r--r-- 1 root root   1212 Feb 12  2020 telnet.fish
-rw-r--r-- 1 root root    939 Feb 12  2020 termite.fish
-rw-r--r-- 1 root root  15550 Feb 12  2020 terraform.fish
-rw-r--r-- 1 root root   1776 Feb 12  2020 test.fish
-rw-r--r-- 1 root root   1028 Feb 12  2020 tex.fish
-rw-r--r-- 1 root root    867 Feb 12  2020 time.fish
-rw-r--r-- 1 root root   1542 Feb 12  2020 timedatectl.fish
-rw-r--r-- 1 root root    351 Feb 12  2020 timeout.fish
-rw-r--r-- 1 root root   6212 Feb 12  2020 tmutil.fish
-rw-r--r-- 1 root root  12476 Feb 12  2020 tmux.fish
-rw-r--r-- 1 root root    728 Feb 12  2020 tmuxinator.fish
-rw-r--r-- 1 root root   1617 Feb 12  2020 tokei.fish
-rw-r--r-- 1 root root    659 Feb 12  2020 top.fish
-rw-r--r-- 1 root root   1349 Feb 12  2020 totem.fish
-rw-r--r-- 1 root root   1406 Feb 12  2020 touch.fish
-rw-r--r-- 1 root root   3025 Feb 12  2020 tr.fish
-rw-r--r-- 1 root root   7234 Feb 12  2020 transmission-remote.fish
-rw-r--r-- 1 root root    271 Feb 12  2020 trap.fish
-rw-r--r-- 1 root root   4942 Feb 12  2020 travis.fish
-rw-r--r-- 1 root root   3197 Feb 12  2020 tree.fish
-rw-r--r-- 1 root root   9973 Feb 12  2020 tsc.fish
-rw-r--r-- 1 root root   2687 Feb 12  2020 ttx.fish
-rw-r--r-- 1 root root    640 Feb 12  2020 type.fish
-rw-r--r-- 1 root root   4411 Feb 12  2020 udisksctl.fish
-rw-r--r-- 1 root root   1159 Feb 12  2020 ulimit.fish
-rw-r--r-- 1 root root    257 Feb 12  2020 umask.fish
-rw-r--r-- 1 root root   1247 Feb 12  2020 umount.fish
-rw-r--r-- 1 root root   1255 Feb 12  2020 uname.fish
-rw-r--r-- 1 root root    513 Feb 12  2020 unexpand.fish
-rw-r--r-- 1 root root   1385 Feb 12  2020 uniq.fish
-rw-r--r-- 1 root root    964 Feb 12  2020 unlz4.fish
-rw-r--r-- 1 root root   1336 Feb 12  2020 unrar.fish
-rw-r--r-- 1 root root   2080 Feb 12  2020 unzip.fish
-rw-r--r-- 1 root root   1581 Feb 12  2020 unzstd.fish
-rw-r--r-- 1 root root    916 Feb 12  2020 update-eix-remote.fish
-rw-r--r-- 1 root root    890 Feb 12  2020 update-eix.fish
-rw-r--r-- 1 root root   1860 Feb 12  2020 useradd.fish
-rw-r--r-- 1 root root   2062 Feb 12  2020 usermod.fish
-rw-r--r-- 1 root root   7038 Feb 12  2020 vagrant.fish
-rw-r--r-- 1 root root   6118 Feb 12  2020 valgrind.fish
-rw-r--r-- 1 root root    120 Feb 12  2020 vared.fish
-rw-r--r-- 1 root root  10138 Feb 12  2020 vbc.fish
-rw-r--r-- 1 root root   1092 Feb 12  2020 vi.fish
-rw-r--r-- 1 root root   2942 Feb 12  2020 vim-addons.fish
-rw-r--r-- 1 root root   3687 Feb 12  2020 vim.fish
-rw-r--r-- 1 root root     27 Feb 12  2020 vimdiff.fish
-rw-r--r-- 1 root root 115486 Feb 12  2020 virsh.fish
-rw-r--r-- 1 root root    534 Feb 12  2020 vmctl.fish
-rw-r--r-- 1 root root    309 Feb 12  2020 w.fish
-rw-r--r-- 1 root root  16776 Feb 12  2020 wajig.fish
-rw-r--r-- 1 root root    952 Feb 12  2020 watch.fish
-rw-r--r-- 1 root root    924 Feb 12  2020 wc.fish
-rw-r--r-- 1 root root   2657 Feb 12  2020 wesnoth.fish
-rw-r--r-- 1 root root   8582 Feb 12  2020 wget.fish
-rw-r--r-- 1 root root     48 Feb 12  2020 whatis.fish
-rw-r--r-- 1 root root   1460 Feb 12  2020 which.fish
-rw-r--r-- 1 root root    142 Feb 12  2020 while.fish
-rw-r--r-- 1 root root   1210 Feb 12  2020 who.fish
-rw-r--r-- 1 root root    982 Feb 12  2020 wicd-cli.fish
-rw-r--r-- 1 root root    424 Feb 12  2020 wicd-client.fish
-rw-r--r-- 1 root root    409 Feb 12  2020 wicd-gtk.fish
-rw-r--r-- 1 root root   2593 Feb 12  2020 wpa_cli.fish
-rw-r--r-- 1 root root   1145 Feb 12  2020 wvdial.fish
-rw-r--r-- 1 root root   1573 Feb 12  2020 xargs.fish
-rw-r--r-- 1 root root    865 Feb 12  2020 xclip.fish
-rw-r--r-- 1 root root   2140 Feb 12  2020 xdg-mime.fish
-rw-r--r-- 1 root root     55 Feb 12  2020 xdvi.fish
-rw-r--r-- 1 root root     30 Feb 12  2020 xelatex.fish
-rw-r--r-- 1 root root   3730 Feb 12  2020 xgettext.fish
-rw-r--r-- 1 root root    894 Feb 12  2020 xinput.fish
-rw-r--r-- 1 root root    772 Feb 12  2020 xmms.fish
-rw-r--r-- 1 root root   2255 Feb 12  2020 xpdf.fish
-rw-r--r-- 1 root root   1108 Feb 12  2020 xprop.fish
-rw-r--r-- 1 root root   4897 Feb 12  2020 xrandr.fish
-rw-r--r-- 1 root root   1225 Feb 12  2020 xrdb.fish
-rw-r--r-- 1 root root   1155 Feb 12  2020 xsel.fish
-rw-r--r-- 1 root root   1997 Feb 12  2020 xsv.fish
-rw-r--r-- 1 root root  10841 Feb 12  2020 xterm.fish
-rw-r--r-- 1 root root   2897 Feb 12  2020 xz.fish
-rw-r--r-- 1 root root  12268 Feb 12  2020 yaourt.fish
-rw-r--r-- 1 root root   8941 Feb 12  2020 yarn.fish
-rw-r--r-- 1 root root    590 Feb 12  2020 yast2.fish
-rw-r--r-- 1 root root   3234 Feb 12  2020 yum.fish
-rw-r--r-- 1 root root    306 Feb 12  2020 zcat.fish
-rw-r--r-- 1 root root  37219 Feb 12  2020 zfs.fish
-rw-r--r-- 1 root root   1543 Feb 12  2020 zip.fish
-rw-r--r-- 1 root root   3112 Feb 12  2020 zpaq.fish
-rw-r--r-- 1 root root  26139 Feb 12  2020 zpool.fish
-rw-r--r-- 1 root root   2461 Feb 12  2020 zstd.fish
-rw-r--r-- 1 root root   1120 Feb 12  2020 zstdcat.fish
-rw-r--r-- 1 root root     57 Feb 12  2020 zstdgrep.fish
-rw-r--r-- 1 root root     60 Feb 12  2020 zstdless.fish
-rw-r--r-- 1 root root   2420 Feb 12  2020 zstdmt.fish
-rw-r--r-- 1 root root  54423 Feb 12  2020 zypper.fish
hacker@commands~an-epic-filesystem-quest:/usr/share/fish/completions$ cat INFO
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/include/config/thermal/gov/user
hacker@commands~an-epic-filesystem-quest:/usr/share/fish/completions$ cd /opt/linux/linux-5.4/include/config/thermal/gov/user
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/thermal/gov/user$ ls -la
total 16
drwxr-xr-x 1 root root 4096 Oct  1 09:04 .
drwxr-xr-x 1 root root 4096 Sep 26 17:11 ..
-rw-r--r-- 1 root root  146 Oct  1 09:04 TEASER
-rw-r--r-- 1 root root    0 Sep 26 17:11 space.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/thermal/gov/user$ cat TEASER
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{U_TVpwFIZlak0VpsZtdSTSZeGja.QX5IDO0wCO5kjNzEzW}
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/thermal/gov/user$
```
Initially, I changed the directory to / as mentioned in the challenge and used ls -la to look for a file
named CLUE or FLAG.
After looking around clues in different directories by ls -la(to list out hidden files and directories as well),
I found the flag eventually by using cat to display the clues.
and finally which led to me finding the flag.
### What I learned
Problem Solving
### References
Instructions in pwn.college.


### Task 12
This challenge asks to make a new directory named pwn in /tmp directory and create a file named college in it.
### My Solve
Flag:pwn.college{0sqCJzuCcSW5FEwPTLvAsSg3tNs.QXxMDO0wCO5kjNzEzW}
```
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{0sqCJzuCcSW5FEwPTLvAsSg3tNs.QXxMDO0wCO5kjNzEzW}
hacker@commands~making-directories:/tmp/pwn$
```
I use cd to change the directory to /tmp and use mkdir command to make a new directory named pwn in /tmp. Then, I used the touch command to create a file named college in it.
Finally, I run /challenge/run to get the flag.
### What I learned
Usage of the mkdir command and that it is used to create new directories where the directory name is mentioned
in its argument.
### References
Instructions in pwn.college.


### Task 13
This challenge asks to find the flag in the hidden directory using the find command.
### My Solve
Flag:pwn.college{0sqCJzuCcSW5FEwPTLvAsSg3tNs.QXxMDO0wCO5kjNzEzW}
```
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.4mK6TfTSUV’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/lib/python3/dist-packages/sage/libs/__pycache__/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat /usr/lib/python3/dist-packages/sage/libs/__pycache__/flag
cat /opt/pmdbg/.venv/lib/python3.8/site-packages/pwnlib/flag
cat /nix/store/7ns27apnn4qj4q6e82x821lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
cat /nix/store/5235j9pw49d133fif58hq6wj5jny6m36-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
cat /nix/store/5n51p1m8glqrsrivf229jdjk6byocn-rizin-0.7.3/share/rizin/flag
cat /nix/store/h88nwp2mbj96yypwnm9b54dhwinmp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
cat /nix/store/s8b491bbp9wwe66kqjbxdwxcv2bp8xl-radare2-5.9.8/share/radare2/5.9.8/flag
cat /nix/store/bnlabj2vsbljhp597ir29151nrghm89w-rizin-0.7.4/share/rizin/flag
cat /nix/store/lhvxjpwmgbcxw9015pglnwd6s6jd15m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
cat /nix/store/5q26hgb1qzpyjrsw20wyjy1x5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
pwn.college{QnJ_kolK4keJv8N2eXvrUiPTnf8.QXyMDO0wCO5kjNzEzW}cat: /opt/pmdbg/.venv/lib/python3.8/site-packages/pwnlib/flag: No such file or directory
cat: /nix/store/7ns27apnn4qj4q6e82x821lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag: No such file or directory
cat: /nix/store/5235j9pw49d133fif58hq6wj5jny6m36-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag: No such file or directory
cat: /nix/store/5n51p1m8glqrsrivf229jdjk6byocn-rizin-0.7.3/share/rizin/flag: No such file or directory
cat: /nix/store/h88nwp2mbj96yypwnm9b54dhwinmp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag: No such file or directory
cat: /nix/store/s8b491bbp9wwe66kqjbxdwxcv2bp8xl-radare2-5.9.8/share/radare2/5.9.8/flag: No such file or directory
cat: /nix/store/bnlabj2vsbljhp597ir29151nrghm89w-rizin-0.7.4/share/rizin/flag: No such file or directory
cat: /nix/store/lhvxjpwmgbcxw9015pglnwd6s6jd15m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag: No such file or directory
cat: /nix/store/5q26hgb1qzpyjrsw20wyjy1x5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag: No such file or directory
```
Using the find command will list out some accessible files containing the name flag in them, out of which each file must be displayed with cat until the correct flag (in line 1122) is found.
### What I learned
The find command takes optional arguments describing the search criteria and the search location. If we don't specify a search criteria, find matches every file. If we don't specify a search location, find uses the current working directory 
### References
Instructions in pwn.college.


### Task 14
The challenge states that there is a program called /challenge/catflag that is hardcoded to read /home/hacker/not-the-flag instead of /flag. We have to use symlink
to fool the operating system to read /flag instead.
### My Solve
Flag:pwn.college{s-wYMv687yB6chQoKFUyjhlEg9E.QX5ETN1wCO5kjNzEzW}
```
hacker@commands~linking-files:~$ rm /home/hacker/not-the-flag
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{s-wYMv687yB6chQoKFUyjhlEg9E.QX5ETN1wCO5kjNzEzW}
hacker@commands~linking-files:~$
```
I used rm command to remove the /home/hacker/not-the-flag and used a symlink to open the /flag instead when referring to the /home/hacker/not-the-flag using the ln -s command. 
I finally ran the /challenge/catflag command to get the flag.
### What I learned
Links come in two flavors: hard and soft (also known as symbolic) links.
A hard link is when you address your apartment using multiple addresses that all lead directly to the same place (e.g., Apt 2 vs Unit 2).
A soft link is when you move apartments and have the postal service automatically forward your mail from your old place to your new place.
In a filesystem, a file is, conceptually, an address at which the contents of that file live. A hard link is an alternate address that indexes that data --- accesses to the hard link and accesses to the original file are completely identical, in that they immediately yield the necessary data. A soft/symbolic link, instead, contains the original file name. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file. In most cases, both situations result in accessing the original data, but the mechanisms are different.
### References
Instructions in pwn.college.
