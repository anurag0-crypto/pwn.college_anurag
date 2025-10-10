# Processes and Jobs
### Task 1
This challenge asks to find the filename of the run file present in the challenge directory which has been renamed into a random
name which we have to find out by listing all the running processes in the terminal(we cannot use the ls command to find the
filename in the challenge directory)
### My Solve
Flag:pwn.college{sTej8kHaW6fx5OuQlgH2P-5Bymk.QX4MDO0wCO5kjNzEzW}
```
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.1  0.0   1056   640 ?        Ss   11:00   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-works
root           7  0.0  0.0 231708  2560 ?        S    11:00   0:00 /run/dojo/bin/sleep 6h
root         132  0.0  0.0   4132  2560 ?        S    11:00   0:00 /challenge/17606-run-21827
root         135  0.0  0.0   2744  1600 ?        S    11:00   0:00 sleep 6h
hacker       137  0.3  0.0 231576  3520 pts/0    Ss   11:01   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       143  0.0  0.0 231940  4160 pts/0    S    11:01   0:00 /run/dojo/bin/bash --login
hacker       152  0.0  0.0 233600  3840 pts/0    R+   11:01   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/17606-run-21827
Yahaha, you found me! Here is your flag:
pwn.college{sTej8kHaW6fx5OuQlgH2P-5Bymk.QX4MDO0wCO5kjNzEzW}
Now I will sleep for a while (so that you could find me with 'ps').
```
I ran the ps command with the aux argument which combines the work of arguments a,u and x.
The a argument list processes for all users, x lists processes that aren't running in a terminal, 
and u does the same for a "user-readable" output.
These can be combined into a single argument aux.
I found /challenge/17606-run-21827 running as a command in the terminal and ran it to get the flag.
### What I learned
The ps command lists the processes running in the current terminal by default.
However, we can specify various arguments to the ps command as mentioned below:
Standard" Syntax: In this syntax, we can use -e to list "every" process and -f for a "full format" output,
including arguments. These can be combined into a single argument -ef.
"BSD" Syntax: In this syntax, we can use a to list processes for all users, 
x to list processes that aren't running in a terminal, and u for a "user-readable" output. 
These can be combined into a single argument aux.
These two methods, ps -ef and ps aux, result in slightly different, but cross-recognizable output.
There are many commonalities between ps -ef and ps aux: both display the user (USER column), the PID,
the TTY, the start time of the process (STIME/START), the total utilized CPU time (TIME), 
and the command (CMD/COMMAND). ps -ef additionally outputs the Parent Process ID (PPID),
which is the PID of the process that launched the one in question, 
while ps aux outputs the percentage of total system CPU and Memory that the process is utilizing. 
### References
Instructions in the pwn.college website.


### Task 2
This challenge asks to terminate the /challenge/dont_run program using the kill command or else /challenge/run won't be
able to run.
### My Solve
Flag:pwn.college{AnQRNCbndXUcOy5GeyT1ZZIoFP9.QXyQDO0wCO5kjNzEzW}
```
hacker@processes~killing-processes:~$ ps ux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
hacker       136  0.0  0.0 231576  3520 ?        Ss   11:49   0:00 /challenge/dont_run
hacker       137  0.0  0.0 231708  2560 ?        S    11:49   0:00 sleep 6h
hacker       139  0.0  0.0 231576  3520 pts/0    Ss   11:49   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       145  0.0  0.0 231940  4160 pts/0    S+   11:49   0:00 /run/dojo/bin/bash --login
hacker       154  0.0  0.0 231576  3520 pts/1    Ss   11:53   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       160  0.0  0.0 231940  4160 pts/1    S+   11:53   0:00 /run/dojo/bin/bash --login
hacker       171  0.0  0.0 231576  3520 pts/2    Ss   12:01   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       177  0.0  0.0 231940  4160 pts/2    S    12:01   0:00 /run/dojo/bin/bash --login
hacker       188  0.0  0.0 233600  3840 pts/2    R+   12:03   0:00 ps ux
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{AnQRNCbndXUcOy5GeyT1ZZIoFP9.QXyQDO0wCO5kjNzEzW}
hacker@processes~killing-processes:~$
```
I listed out all the current working processes for the current terminal and found the PID of the /challenge/dont_run
program which is 136. I ran the command kill 136 to terminate the /challenge/dont_run and finally ran /challenge/run
to get the flag.
### What I learned
The kill command terminates a process in a way that gives it a chance to get its affairs in order before ceasing to exist.
The PID of the program we want to terminate must be mentioned in the argument of the kill command.
The sleep is a program that simply hangs out for the number of seconds specified on the commandline in its argument.
### References
Instructions in the pwn.college website.


### Task 3
This challenge asks to interrupt the /challenge/run program by holding down the Ctrl key and pressing C 
to obtain the flag.
### My Solve
Flag:pwn.college{8iyQPd5QcZXIDIo56lNVyYXrew8.QXzQDO0wCO5kjNzEzW}
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{8iyQPd5QcZXIDIo56lNVyYXrew8.QXzQDO0wCO5kjNzEzW}
hacker@processes~interrupting-processes:~$
```
I simply typed /challenge/run and interrupted it by holding down the Ctrl key and pressing C to obtain the flag.
### What I learned
We can press Ctrl-C to interrupt whatever application is waiting on input from the terminal and, typically, 
this causes the application to cleanly exit.
### References
Instructions in the pwn.college website.


### Task 4
In this challenge, there's a decoy process that's hogging a critical resource - a named pipe (FIFO) at /tmp/flag_fifo 
into which (like in the Practicing Piping FIFO challenge) /challenge/run wants to write my flag. 
I need to kill this process.
### My Solve
Flag:pwn.college{kcQmUTgk8DZpGEhOLV4f3-8F6v5.0FNzMDOxwCO5kjNzEzW}
```
hacker@processes~killing-misbehaving-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   12:38   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-works
root           7  0.0  0.0 231708  2560 ?        S    12:38   0:00 /run/dojo/bin/sleep 6h
root         137  0.0  0.0   4132  1280 ?        S    12:38   0:00 /bin/bash /challenge/.init
root         138  0.0  0.0   4132  1280 ?        S    12:38   0:00 /bin/bash /challenge/.init
root         140  0.0  0.0   2744  1600 ?        S    12:38   0:00 sleep 6h
root         141  0.0  0.0   2744  1280 ?        S    12:38   0:00 sleep 6h
hacker       144  0.0  0.0 231576  3520 pts/0    Ss   12:38   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       150  0.0  0.0 231972  4160 pts/0    S+   12:38   0:00 /run/dojo/bin/bash --login
hacker       159  0.0  0.0 231576  3520 pts/1    Ss   13:40   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       165  0.0  0.0 231972  4160 pts/1    S+   13:40   0:00 /run/dojo/bin/bash --login
hacker       179  0.0  0.0 231576  3520 pts/2    Ss   13:42   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       185  0.0  0.0 231972  4160 pts/2    S+   13:42   0:00 /run/dojo/bin/bash --login
hacker       199  0.0  0.0 231576  3520 pts/3    Ss   13:46   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       205  0.0  0.0 231972  4160 pts/3    S+   13:46   0:00 /run/dojo/bin/bash --login
hacker       218  0.0  0.0 231576  3520 pts/4    Ss   13:48   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       224  0.0  0.0 231972  4160 pts/4    S    13:48   0:00 /run/dojo/bin/bash --login
root         239  0.0  0.0   5788  3200 pts/4    S+   13:52   0:00 /bin/bash -c . "/challenge/run" /challenge/run
root         241  0.0  0.0 231972  2560 pts/4    S+   13:52   0:00 cat /flag
hacker       242  0.6  0.0 231576  3520 pts/5    Ss   13:56   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-inte
hacker       248  0.0  0.0 231972  4160 pts/5    S    13:56   0:00 /run/dojo/bin/bash --login
hacker       257  0.0  0.0 233600  3840 pts/5    R+   13:56   0:00 ps aux
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{qFgTqYeQ-A0ikfnNF2pRJHo7A5DxEzsYt-50raJ.FLZizIE}
pwn.college{Gb9VOLUoRsX7oT87l61XCnC45rStW78jcpztcPG5C5NWsY2}
pwn.college{JdTGfLYbNiMS21vLU.dBSbUqo-8Z-F8zVeQ4g414CiDsVpn}
pwn.college{84IaQywN3by-547-5jyV8UX-THGvYMiw1Sc8W9wcySbezBj}
pwn.college{9fgOpvIL4c.UeIkON8b2OMqgO6huGUzrFrJS4VkZDTeqt5q}
pwn.college{P6EyPZDjmXbQcUk4YXgc3GAscwW0GDEuLH2.lAbO7E5sFpj}
pwn.college{RjlKBERZ1J.ElVJwwbqZtrOK8CTXR6Dt9.IiEJ50HjBgdik}
pwn.college{hnqxbCR1L9z5pTEFfCoCPzY.H-WqibDf0GBbBC.Sjd2DNVJ}
pwn.college{2X4Oy.yBW7eVjyMRlHKEyqgs3JBsWtXeieRmknBU937QDim}
pwn.college{-1QcEWhHOZdcdez1Uw0MZK8c-YmETFk0ZJvvFUc9u0pJLmg}
pwn.college{lEbyYcbuY8-9TcOrBgjrQgRHshjKT7mjjS2TEx5h0yBQ0WJ}
pwn.college{uKjXMQcD9y8uEu2SQYnH0HhUQ5JCJtZp3YTIXkvEat3MNhX}
pwn.college{S8sZH2c-fIIqAoWa9bX9r2tSX6mLnyatQCXJimf1KjCvwkR}
pwn.college{JzeqidxewUr14XA03NhDWlgkuaMqC3HUyO.d4BvoWxtEIuV}
pwn.college{jhvtWMAE0CelhUlBAUMCleN1iIKMk8CE67Hi8GLNYqMldCl}
pwn.college{Tf.UuLSPv2x0bLHqFPWxKRDM.LoOS4VDSh-IasIx7dpIkm.}
pwn.college{8e.4dOC3bdjh0MUgamrL4VnW4wXzsy.s2mqupfev.4jHMCb}
pwn.college{q8v3S4magYqEwfCbsVbEAbXsvvxGCRyuTrB-hZE-4aIJZiF}
pwn.college{RVMVrgHdPURiqnX.amM8b4tlV0MBPhDMJHbYzRMzWr-FCeu}
pwn.college{M11tKtwIGIMcFG5KtjN2wN0A5dKENjKBq34EfDV.4C42xAK}
pwn.college{PX8M3fQq3SCD78EcsP-Z2kFiRURhMilDhaX0SHKoDmr4LXj}
pwn.college{mkVhE1xuA4SuU99KtdZcdd7xFOXi6MKSabgx6n22W.QFPiS}
pwn.college{GXlCrbORBhOvnCOGePNziZtWxtSsF5B21Jzx4ve54oHC4kO}
pwn.college{.c4iEJT9PB8F7i46ASfRfaGu.CcHx3hR3AHY3IZhcO5J-I8}
pwn.college{c0gmPb87wocSv31UhdAeIq8KhwukOFEPpBiGgYQCMRvu3hh}
pwn.college{cHLgFMc6Chqip-eVpEHaT64FmLe6z6ZIA0j2feyZ9UieJ.O}
pwn.college{0ecYLhdzlIOkz19XsUKCBA8a-0GzAkLLhrQ3MrSWgZjFOlR}
pwn.college{IF5.DJ3pxT8f.2omZPD.CqLqbBzIttum.wrVUCLGmRUwWfo}
pwn.college{T5AmzVfUHzgiueQ9vmN4KuXt8RD2Iqt1LUParHX9xL64Ee3}
pwn.college{gEYCmxjZBpc3tcAvQmTa8kd16W3cCb27.00meCAeIySAGCP}
pwn.college{v0eJH2Q7Qr9QATf6WU-oz8ZXU8kt5xFRdWofD6sF3B43Sqi}
pwn.college{KjwNKsLZLxgI1yBn78tS7irj2Pn3xwQjgwRhdR1JW7D91C8}
pwn.college{H3ru9RM-6UJXozWQ9eMsi.Yu1z1NkL2dMAX1WarCCAN7nsT}
pwn.college{Wvr7bnP98fi2VwBBN116ZwxO-bMEBzPArpoSnCg5fhmEhMK}
pwn.college{KVnOBpc9fJFtc7s2zUj1Wc8iyl3RmYjNd6MMryQBxNCrdEo}
pwn.college{js-11Tyey7epKf64USUDKZcNnMy3npjfxfyqUmqIAoE5JO3}
pwn.college{sUMDI.g8654JISF9PLO-ITeVkU4IKqIKdbiyLjF7twyKOL1}
pwn.college{bZm5GDfGqCZH21FYKeIa4RUt.YNNPXWPTz69SX761ECxtw.}
pwn.college{pTfq7bDQeRtBZNKp.XkhEdN.FD.J5qwF-L-1heioRvsNfd2}
pwn.college{Rlg9Mdu2TJjF3emotfTmQmHubmKHlSWCjTHkk1j6Qy.AJ88}
pwn.college{dka5mgMa.5kMcIsMj51akhmmgmS6iVChfAIfiQuSh2uHJf7}
pwn.college{KTsJAY3TredcfnvR8Kg5-QSRbw6rsA8mjd9QZlQIEiYkC6U}
pwn.college{ogY.LHQNVPvBThYTF4wLfEkY5Bipy80yYy1w7tLQ3MqYVre}
pwn.college{WPZbjIcOhPFQAMGkPdP7Mg-NC-ht2qyOOVa03kNIssPQiUF}
pwn.college{dy-oCd1F7ZWvDUBPOhZR3kL0DL0Y5iDQJhieKiyesYsn8jA}
pwn.college{d6M4Ah-dWVdfHThqmwodRAtgwVnVC8BoiQohF96OdonS3N6}
pwn.college{QvwVixGV39x81p4Xr0Rf2eCJnADPfyW42-DMZb02fQrTiC.}
pwn.college{XOs.-Si76EAJGeUkU8N5uGNrQRLHZUEg7DWr4H1BGHFLbHf}
pwn.college{MNYis9fC3P6SjH1DeC6gsFkJACJxSZFJVZADBOP2fBWBxD7}
pwn.college{MI3EhjpE7iKNJk9Yz7rqq8d7XLXRFTBC9KR88Bs8icerkez}
pwn.college{aCkX9SfykwN0QJQenlCCz-hK3kr4WBPsGuCH9iW0zsyDqnH}
pwn.college{5c.UxKUI4HVqgTuDnk1AB-J8s.Lsf6vGyQx6R.HWY2v5day}
pwn.college{8lGYWh7jSbaKoyVJX9mYOY.WVoeMszJLNeC.kyf47.qQHWv}
pwn.college{jWWvgxfPAkZfTQAQagxEY2oxJ17LGfwpY2m7l6TiM1f7G5O}
pwn.college{urJaYyLLtKEndqtc7Lp69-CuBRQeugjUpeFHSDpWRHDWF.z}
pwn.college{S.Cj0wyAB1CjGlcebrMOqiC18D6PFjJESKneHNDA4BFTdPi}
pwn.college{LUscM1h2TFqS5.bTmEWapkYOnVnHwmcFVm47hc1cqkM0V2L}
pwn.college{i0kZpiFTGNYspOMhPxjmu5G8CZE26Hfrsu8sDw0dO1KcznS}
pwn.college{2C18qJd.uU1Jssaon7BeLY9XFeyRdPtM6xSkMBYXZEdnU5R}
pwn.college{POyQAluBFLo29z1nsDso7cvSWfs1hK-NrEkBE8Hg8JeUA9A}
pwn.college{JMxHOIOirfAHTrmyCOvysz5Wtz2gRurQIIEl5L5ci6Yrdyc}
pwn.college{82WtyDIi3S3jMc8WmzOjlAXqP0AnPzbKBW1XFZHh8cAtJwT}
pwn.college{D7NTIG7XE0UOZGHBt3zkWWL91EEGgiOONLXI27rm-nJWYr.}
pwn.college{3sbFS7GrEhLT.4Ki6Vw5yWIAUxY3cssHwcU2TtOkjlHUI9p}
pwn.college{pB6q-mCZZSmQpRVi8ZakO4BuC9xPzW5.6TaqFiMnH7aRec4}
pwn.college{-wOcxV3S5S1YgynHb8ZzZwY9DFNvWH-GAbcNpK0Xq.OLjRu}
pwn.college{OAFYVxMymbbdZaNc5M0Ps2JkmdRw7R45OQwYpfUrcImZrtB}
pwn.college{fHJe387kddhyjzeDG.LKVhXMETRNiJb1QlK4yD3owG05SlD}
pwn.college{Jnjzg-hg0bABbbhSuTmIHdYv.Iv3T5Vhfa66vecuEpLDNXp}
pwn.college{BeOOoRYpi4-b3lfYgu59jzqaikTwVr7UkvB8g2zezxDS1f0}
pwn.college{0rTycldMlHclDPqSHy97HKoA6Lnln1WL3X0ImsqWNt8XE6g}
pwn.college{lri4mokqi6J30nWQTALcYVgrsIXMEfQFYYYLUn.BlGeeGXW}
pwn.college{mJDwldll-qO.ReA4TvyHbsdxEztbNOY3VAKHrkWHfESgn.B}
pwn.college{yf8o2NDs7PoTO4UnBb-xV9odJ2llcdvJrV9-mXK0AeUPL24}
pwn.college{kZOztMC9Ee8YveLKWJR-X2PWQmWPNX2cdTMEQDtY-1KTex1}
pwn.college{h-x9qNHYANskgsitUJ6sMQdxhDCFAaABImcAW5V2VHoFu0V}
pwn.college{Lv0GjoRR45ESyzPgNF1qHav4dqZdc-l7oCaKOSxTBccBJRu}
pwn.college{Tnovw4PF4lLnvVwUUfskRmw1JM0-zW1pTLQ4Kc-X2DjP.6t}
pwn.college{sIOWFcd-i77mXb7Wyqd.i762cfVoym4aoZ5doLWI2jwBc6a}
pwn.college{nxHubr5e6hA3cNfqXyvXVhBHNjJTpyXvC1xYnb4mhK2JzCd}
pwn.college{OmRLTLh3dIf.J7iyiVVNtvpuo9-MhoAVa7n97JeYhydb.gi}
pwn.college{uVA1UwOi6Ga13Sy8GCY1eIqJLNc.KfCLdiu-ve8hOjiw9qj}
pwn.college{a0cV2ry2BxDSW8uEI-wq8ozTxcfgy4EYMKWMvmQ8ZKkZlL8}
pwn.college{0xk1RrEPrEi3IoJPUixErGnFomZtwkX5Tev.OPx2v7NtPY3}
pwn.college{z9WQSRudCopUNhLRQsckMJrLMdOtwmKC8h1Azu2UAssQCOf}
pwn.college{fhjuwwZpD26gs4sQ5kKUz6R7fWmMT4fXS5AO0wAwGsfl0JZ}
pwn.college{cYcE0T8ZO083kPpq0XJBhzkceGsmC91A5rnoUniGiyyzK-m}
pwn.college{S7r6R90HiyPFifr0WcYuhJxEye2zV3HIkVgNFrS0Y8i4Q9K}
pwn.college{BGdbzGy8ridRj93.Z4k8cAvgQfL9ut.uJwjXfKm2ZiIJP2t}
pwn.college{mveUGhqRmd9ye69LuugRsmdZ4MJY94By41j5VSqwSS6D39-}
pwn.college{4TNft40pcTJHY1XITf0xOvbkyD79z-aXsmlrwtnCLG4OvL7}
pwn.college{7BvrXIN-OYeHawYf.mKGSFtoDXiZ-hMlryGbCsQ5Zk-vuog}
pwn.college{xZe0RRUToRj9NbJPUY9N1NaEWkOfWSLMUNpDkZl7NT.HGGz}
pwn.college{MpGO1xKh7pb.WfiQjPe7742NYuit5P3UmgGys5cYK9g6dCR}
pwn.college{O-5R3hbxnmZD8bjOiQspk.aVpDMyrytz1Zg.-VUczx5xKa-}
pwn.college{ARpgLUWPvvGv7rDIqXkHTYPO3.1HUWQNfTXssjf4RAUYv5a}
pwn.college{BVxcUHgeVkCQWSk9DE5bpZs.OpHvb35FDSpOinTzAfk7res}
pwn.college{2FTjJSkNMuyA3AvHpVrIOeTfOF0kDmH-ikwfDIT1Iy8beIC}
pwn.college{BvltYLJ73LCMpBj9083E8dJObAl6HDzKlJKGex6B3KU4G7N}
pwn.college{S4uqKGlT0k.cbAFxsHoOj6OA5cL.oDMXyal9Wd1s4P5Oezl}
pwn.college{nq6Hc2q06-LxGIZ22PoCP6CHqCeQZQF-SMopt.4.cZhNyii}
pwn.college{IwGodG0ivLuUvGgk10UBYgfcofyHUjMqyhEr5dVoNKVVCVT}
pwn.college{6lIMnIvwcLg4hZeLTTrJTFIHz0DW.Cnq1.UBeHbCOcW9jM7}
pwn.college{mLln3LNe88ARQEIJ05BRXttU--m6WUCYakT21lL3VuRIz2w}
pwn.college{u07CBm03.fgOsKUeZSCpozsTPm-T8iUY4yB6RGQXQwPMscE}
pwn.college{VxvcnRlM4FPw5P1sZ8tkVvDacIjno1Xf.TRCMyz6fwF6NfO}
pwn.college{yihDUshIm74G-dFrE0K1lfeoPueZxWubU4P5l9jCSFhWBI9}
pwn.college{AGMbkxRbeRW51MnFz8ddiry7zh5RZYxBCsrdFMMpIHahavO}
pwn.college{qt6cHIivXcgoiqNf.YdznS3JHSvzh6-6cA1jVD8-X9F3gln}
pwn.college{j3dpSpLYce12.LRww99N8D1W-O1MogXX5yjTqQLHpOQgZoC}
pwn.college{r4VOdn4mtAqMVAtaw79dl9jCni5R-v3azhd0Yhz0Q5U52p3}
pwn.college{hx090CaCaOfBxMkrQlJxLuq-SlbMkc3Lu2RTKbql6VAbUQi}
pwn.college{Kp2vVcanpGNo.TILSDybSEIfpq2ivhphbuYZz0zYGuzVnNn}
pwn.college{VAZ6KRmn9mSMONrERvVgPYvVyhUKNoETJlRydxSNqXUd08t}
pwn.college{KXkR9HcHjmBk-.KDOFsp9sd4Bs1AQ3.vrLri2PVcW1Po7cO}
pwn.college{S6.Kf-6KEAi1u31ErljwcjKPFdNCySboTDRFh92lAIThDfp}
pwn.college{ZxoTugEf22xWMy.eAjrW933KfIYAbYTRGo6yBndv9Mv7XKa}
pwn.college{hfsMWLIyzLao6tzgAinVyKb8N59SVZguqURR3ElraEnTOEa}
pwn.college{Lw1wtQVqsODRtxEMKOVzmogDa85FNsOawZcYeb0fzgwVe5n}
pwn.college{1zMJyyEhGP1Kn6rp8n12M12XUok4Zck.xkZl8Lgzu.zTn02}
pwn.college{2tk9AxtW-QvXtSly.61qRgU.u3mL-X626u.B0vXvR5LSvBv}
pwn.college{.fIIUhByX6FejxM2uKkhixqPCWF0KDyfcDAwlkgSL-CPq1X}
pwn.college{fgb9LsgWplR3xO3EdpP0k0nfCYJZq0aovsK56t.NjzQ7gN0}
pwn.college{myptHBCYOWle449HFYkKbVrRaUKSw4Ouaegjz5LYTvpLf81}
pwn.college{tZgZ7mVX3AVoG6JgaLYpfcalLoiOnRw2sOG.9gPz4ly-rny}
pwn.college{75aoD4G0VoMHfD1Of0VjI13gnUsw4i.0woIWbtFEFNf-NmD}
pwn.college{XbCq-x3C9JAgXaJWazOAMUSBrDvyKkTvxw2aV8x6szscr0w}
pwn.college{KnbadNTdIsuUcjBSdfIwS-L3I4gjkvT.7kpQk8xrAIFEm8G}
pwn.college{BsUROx70SqVgV4DuW8sNLmFdt1O3.vtrI3BetC9xNISO1cj}
pwn.college{P4T9UbfT2MkVrjATQarHrVr766O.feHDzDufj3aL3kMWe6H}
pwn.college{W2DmAnzuluQPyc9IFdHuV3i8zhaSg3OnVqmSC7murBk4BEs}
pwn.college{yemsiItvERCmdfWFZWBEKXO857fw1IKvB7vAUABkKqTXB1j}
pwn.college{QvZ4tP13EHmVvCDBlMeUmm02FUZ1DkHScxsmdJ2M.eXPJGM}
pwn.college{JFKpNkahVVgY2S-qemQQv2xyO.BRNz6khUYhgeOSAsE16y2}
pwn.college{kcQmUTgk8DZpGEhOLV4f3-8F6v5.0FNzMDOxwCO5kjNzEzW}
^C
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{kcQmUTgk8DZpGEhOLV4f3-8F6v5.0FNzMDOxwCO5kjNzEzW}
```
In this challenge, I ran ps aux initially to view all the running processes in the current terminal. I found the PID
of the challenge decoy program and terminated using the kill command. Then, I displayed /tmp/flag_fifo using the cat command
which printed many decoy flags with the real flag as Linux pipes are buffered: conceptually,
they have a sort of length through which data flows, and we might kill the decoy process 
while data is in the pipe. That data, having already entered the pipe, will proceed to the other end (your cat).
I ran /challenge/run and used the cat command on the FIFO file to finally print the real flag.
### What I learned
Linux pipes are buffered: conceptually, they have a sort of length through which data flows, 
and we might kill the decoy process while data is in the pipe. 
That data, having already entered the pipe, will proceed to the other end (your cat).
### References
Instructions in the pwn.college website.


### Task 5
This challenge asks to interrupt /challenge/run using a less drastic process which is Ctrl-Z
### My Solve
Flag:pwn.college{w-BhHhpb4sEvp6q1swX4y1W89CD.QX1QDO0wCO5kjNzEzW}
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         168     159  0 14:12 pts/2    00:00:00 bash /challenge/run
root         170     168  0 14:12 pts/2    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         168     159  0 14:12 pts/2    00:00:00 bash /challenge/run
root         175     159  0 14:13 pts/2    00:00:00 bash /challenge/run
root         177     175  0 14:13 pts/2    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{w-BhHhpb4sEvp6q1swX4y1W89CD.QX1QDO0wCO5kjNzEzW}
hacker@processes~suspending-processes:~$
```
I simply ran /challenge/run and suspended it by holding Ctrl and pressing Z. I ran /challenge/run again
to get the flag.
### What I learned
We can suspend processes to the background with Ctrl-Z.
### References
Instructions in the pwn.college website.


### Task 6
This challenge asks to suspend /challenge/run and resume it again using a builtin fg.
### My Solve
Flag:pwn.college{4nuUmEDV7UmjsfHEA7c3e_K5fhE.QX2QDO0wCO5kjNzEzW}
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{4nuUmEDV7UmjsfHEA7c3e_K5fhE.QX2QDO0wCO5kjNzEzW}
Don't forget to press Enter to quit me!
```
I suspended /challenge/run by pressing Ctrl-Z and resumed it again by using the fg builtin.
### What I learned
To resume processes, the shell provides the fg command,
a builtin that takes the suspended process, resumes it, and puts it back in the foreground of the terminal.
### References
Instructions in the pwn.college website.


### Task 7
This challenge asks to resume the /challenge/run after suspending in the background of the terminal.
### My Solve
Flag:pwn.college{83U0UyUfIVlaDCsbWYgDQe_OTl1.QX3QDO0wCO5kjNzEzW}
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{4nuUmEDV7UmjsfHEA7c3e_K5fhE.QX2QDO0wCO5kjNzEzW}
Don't forget to press Enter to quit me!

Connected!
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         153 S+   bash /challenge/run
root         155 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

hacker@processes~backgrounding-processes:~$
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         153 S    bash /challenge/run
root         163 S    sleep 6h
root         164 S+   bash /challenge/run
root         166 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{83U0UyUfIVlaDCsbWYgDQe_OTl1.QX3QDO0wCO5kjNzEzW}
hacker@processes~backgrounding-processes:~$
```
I simply suspended the /challenge/run and used the bg builtin to run it in the background of the terminal.
I ran /challenge/run again to simultaneously run it in background and foreground and got the flag.
### What I learned
The bg builtin allows us to run the suspended process in the background of the terminal.
### References
Instructions in the pwn.college website.


### Task 8
This challenge asks to foreground the backgrounded process which I did similarly to a suspended task in the previous
task.
### My Solve
Flag:pwn.college{s0nmxAmNBGcdwnktml417GjeUj-.QX4QDO0wCO5kjNzEzW}
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{s0nmxAmNBGcdwnktml417GjeUj-.QX4QDO0wCO5kjNzEzW}
hacker@processes~foregrounding-processes:~$
```
I simply suspended /challenge/run, put it in the background and put it on the foreground of the terminal using
bg and fg builtin respectively.
### What I learned
We can put backgrounded processes on the foreground as well just as we can for suspended processes in the terminal.
### References
Instructions in the pwn.college


### Task 9
This challenge asks to directly launch /challenge/run on the background without suspending it first.
### My Solve
Flag:pwn.college{AceKk3-iuBd0tlaFleNAE_RKKfu.QX5QDO0wCO5kjNzEzW}
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 138
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{AceKk3-iuBd0tlaFleNAE_RKKfu.QX5QDO0wCO5kjNzEzW}
```
I simply ran /challenge/run & to directly launch it on the background.
### What I learned
We can directly launch processes on the background of the terminal by appending & to the command.
### References
Instructions in pwn.college website


### Task 10
This challenge asks to retrieve the exit code of /challenge/get-code and pass it as an argument to /challenge/submit-code 
to get the flag.
### My Solve
Flag:pwn.college{cjaATHQ2IQSytF4c79XxZvrt9vh.QX5YDO1wCO5kjNzEzW}
```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
189
hacker@processes~process-exit-codes:~$ /challenge/submit-code 189
CORRECT! Here is your flag:
pwn.college{cjaATHQ2IQSytF4c79XxZvrt9vh.QX5YDO1wCO5kjNzEzW}
hacker@processes~process-exit-codes:~$
```
I simply ran /challenge/get-code and ran echo $? to get the exit code of /challenge/get-code which is 189
as shown in above. I ran it as an argument to the challenge/submit-code command to get the flag.
### What I learned
Every shell command, including every program and every builtin, exits with an exit code when it finishes running
and terminates. This can be used by the shell, or the user of the shell  to check if the process succeeded
in its functionality (this determination, of course, depends on what the process is supposed to do in the first place).
We can access the exit code of the most recently-terminated command using the special ? variable. 
We need to first prepend it with $ to read with echo as it is stored in a variable.
### References
Instructions in the pwn.college website.


























































