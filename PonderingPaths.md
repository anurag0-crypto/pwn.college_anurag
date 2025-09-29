
# Pondering Paths
### Task 1
The challenge asks to invoke the pwn program using its absolute path.
### My Solve
Flag:pwn.college{MJoHj2bcHojK8KTBbGSAf5hAA88.QX4cTO0wCO5kjNzEzW}

I launched a terminal and invoked the pwn command from its absolute path typing /pwn to get the flag.

### What I learned 
I familiarised myself with the command line.

### References
Instructions in the pwn.college website.


### Task 2
The challenges asks to execute the run file that is in the challenge directory.
### My Solve 
Flag:pwn.college{oneaYZNtGlkVvfGZkxBaOuXBFwU.QX1QTN0wCO5kjNzEzW}

I launched the terminal to type /challenge/run to execute the run file in the challenge directory and hence got the flag.

### What I learned
I familiarised myself with the command line.

### References
Instructions in the pwn.college website.


### Task 3
This challenge asks to execute the /challenge/run program from a specific path.
### My Solve 
Flag:pwn.college{Ip9GWT7Xzer_2UTrDfgjik1zkVt.QX2QTN0wCO5kjNzEzW}


I ran /challenge/run command which told me to switch to a specific directory. I used the cd command to change to that directory and ran /challenge/run in the terminal
to get the flag.

### What I learned
I familiarised myself with the command line.

### References
Instructions in the pwn.college website.


### Task 4
This challenge asks to execute the /challenge/run program from a specific path.
### My Solve
Flag:pwn.college{4V6uaSsrVZmJn95U9F-cc0rVruo.QX3QTN0wCO5kjNzEzW}


Exactly same as earlier task.

### What I learned
I familiarised myself with the command line.

### References
Instructions in the pwn.college website.


### Task 5
Same as Task 4
### My Solve
Flag:pwn.college{8_Px5wBjLUM3RrOVHWHRcUrg9F2.QX4QTN0wCO5kjNzEzW}

Exactly same as earlier task.

### What I learned
I familiarised myself with the command line.

### References
Instructions in the pwn.college website.


### Task 6
The challenge asks to invoke the /challenge/run command using a relative path.
### My Solve
Flag:pwn.college{sQtqbU1q3AeGa57SG458zUVYc2e.QX5QTN0wCO5kjNzEzW}

I type cd / to change the directory to / and write challenge/run which is a relative path to /challenge/run and hence get the flag.

### What I learned
Understood the concept of implicit relative paths.

### References
Instructions in the pwn.college website.


### Task 7
The challenge asks to invoke the /challenge/run command using . in the relative path.
### My Solve
Flag:pwn.college{80uSc8KPKg6y4IDic4NWJFHetB5.QXwUTN0wCO5kjNzEzW}

In the directory of /, i wrote ./challenge/run which is an explicit relative path to /challenge/run(absolute directory) to get the flag.

### What I learned
Understood the concept of  explicit relative paths.

### References
Instructions in the pwn.college website.


### Task 8
 This challenge asks to run the required /challenge/run command from the /challenge directory using a . in the relative path.
 ### My Solve
 Flag:pwn.college{UPCkMDgq4LMfoGIqwXAUk-pEjg7.QXzMDO0wCO5kjNzEzW}

 As this challenge required to execute /challenge/run from the challenge directory, i first used cd to change the directory to /challenge. After doing so,
 typing ./run helped me get the flag.

 ### What I learned
 More clarity in relative paths.

 ### References
Instructions in the pwn.college website.


### Task 9
In this challenge, the /challenge/run command will write a copy of the flag to the specified file given as argument to the command. Also, this challenge has some constraints:
1.Your argument must be an absolute path.
2.The path must be inside your home directory.
3.Before expansion, your argument must be three characters or less.
### My Solve
Flag:pwn.college{A9SPP_Rlaa-LSrjJWtV3tWbxShD.QXxcTN0wCO5kjNzEzW}

To complete this challenge, I wrote /challenge/run ~/a where ~/a is the argument of a file named a which extends to the absolute path as well is of three characters.
Running the corresponding command, copies the flag to the file. After this, displaying the file using cat helps me fetch the flag.

### What I learned
Problem solving

 ### References
Instructions in the pwn.college website.
