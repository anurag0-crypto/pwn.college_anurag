# Data Manipulation
### Task 1
This challenge asks to use tr to swap the case of the flag obtained by running the /challenge/run command which will
be the necessary flag for the completion of the challenge.
### My Solve
Flag:pwn.college{MJHJ9EFpPD8qDRye4TTRAwUcnEI.01MxEzNxwCO5kjNzEzW}
```
hacker@data~translating-characters:~$ /challenge/run | tr 'A-Za-z' 'a-zA-Z'
yOUR CASE-SWAPPED FLAG:
pwn.college{MJHJ9EFpPD8qDRye4TTRAwUcnEI.01MxEzNxwCO5kjNzEzW}
```
In this challenge, as the goal is to swap the case of each character in the flag..I passed two arguments to the tr command:
Initially, the uppercase characters get converted to lowercase and then the lowercase characters get converted to uppercase.
So, I typed /challenge/run | tr 'A-Za-z' 'a-zA-Z' that will swap the case of the output of /challenge/run..which is the flag.
### What I learned
The tr command translates the character provided in its first argument to the character provided in its second argument.
### My References
Instructions in pwn.college website.


### Task 2
This challenge asks to delete the ^ and % characters present in the flag and hence obtain it by using the tr command with a 
special argument -d
### My Solve
Flag:pwn.college{ctseCPz_Yy3URsIm8hye4jzNW0m.0FNxEzNxwCO5kjNzEzW}
```
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^ %
tr: extra operand ‘%’
Only one string may be given when deleting without squeezing repeats.
Try 'tr --help' for more information.
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^
Your character-stuffed flag:
pwn.%c%o%l%l%eg%e{c%ts%eC%P%z_Yy%3UR%s%I%m8%h%ye4%j%z%N%W0%m.0FNxEzN%xwC%O5%k%j%Nz%E%z%W%}%
hacker@data~deleting-characters:~$ echo pwn.^col^l^e^ge^{ct^s^e^C^Pz_Y^y^3^UR^s^I^m^8h^y^e^4^j^z^N^W0^m^.0FNxEz^Nxw^C^O^5^k^jN^zEz^W^}^ | tr -d ^
pwn.college{ctseCPz_Yy3URsIm8hye4jzNW0m.0FNxEzNxwCO5kjNzEzW}
hacker@data~deleting-characters:~$
```
As the website does not give information of whether we can pass multiple arguments for deletion with the special argument
-d, I tried deleting both ^ and % at once. As, it did not work, I first thought of deleting ^ and then %. Finally, I
obtained the proper flag.
### What I learned
The tr command can be used to delete one specific character at once by specifying the special argument -d from a string.
### References
Instructions in pwn.college website.


### Task 3
This challenge clearly asks to delete a bunch of newlines injected into the flag using the tr's -d flag.
### My Solve
Flag:pwn.college{4AFiTWZJ3F1XOKPopcbMnzNyCch.0VNxEzNxwCO5kjNzEzW}
```
hacker@data~deleting-newlines:~$ /challenge/run | tr -d '\n'
Your line-split flag: pwn.college{4AFiTWZJ3F1XOKPopcbMnzNyCch.0VNxEzNxwCO5kjNzEzW}hacker@data~deleting-newlines:~$
```
### What I learned
Representation of the newline character '\n'.
### References
Instructions in pwn.college website.


### Task 4
This challenge asks to fetch the output of /challenge/pwn and pipe it through the head command to grab the first 7 lines and pipe them onwards to /challenge/college to finally get the flag.
### My Solve
Flag:pwn.college{0XOcpi9mqbqzuM2rTnpKSO3zsMM.0lNxEzNxwCO5kjNzEzW}
```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{0XOcpi9mqbqzuM2rTnpKSO3zsMM.0lNxEzNxwCO5kjNzEzW}
hacker@data~extracting-the-first-lines-with-head:~$
```
Using the pipe operator, I fed the output of /challenge/pwn as input to the head command which only sorts out the
first 7 lines and those 7 lines are fed as input to the /challenge/college command to finally get the flag.
### What I learned
The head command is used to display the first few lines of its input. By default, it shows the first 10 lines, but we can control this with the -n option: where n is the first n lines which we want to display.
### References
Instructions in pwn.college website.


### Task 5
In this challenge,the /challenge/run program will give us a bunch of lines with random numbers and single characters (characters of the flag) as columns. We need to use cut command to extract the flag characters, then pipe them to tr -d "\n" to join them together into a single line.
### My Solve
Flag:pwn.college{0BuwRyZ6YWym3GGwBWtGuFJYWKB.01NxEzNxwCO5kjNzEzW}
```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{0BuwRyZ6YWym3GGwBWtGuFJYWKB.01NxEzNxwCO5kjNzEzW}hacker@data~extracting-specific-sections-of-text:~$
```
In this challenge, I used the cut command to extract the second column among all the lines and used tr -d "\n" to delete
all the newlines which contained the flag characters.
### What I learned
The cut command can be used to extract specific lines among lines of text where the format of the command is
cut -d delimiter -f N where delimeter is the character from where the columns will get separated and N is the column number
which is to be extracted.
### References
Instructions in pwn.college website.


### Task 6
In this challenge, there's a file at /challenge/flags.txt containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be found at the end.
### My Solve
Flag:pwn.college{QezCrCSNlO6wqTaUWHyokDSr7yH.0FM0MDOxwCO5kjNzEzW}
```
hacker@data~sorting-data:~$ sort /challenge/flags.txt
ovm.bolkdgd{PezBrBRMlO5vqTaUWHxnjDSr7xG.0FM0MDOwwCO5kiNzEzW}
ovm.colldfe{PezCqBRMlO5wqTaUWHynkCRr7xG.0FM0MCNxvCO5kjMzEzW}
ovn.cnklefe{QezBrCSMlN6vqTaUVHxokDSr7yH.0FM0LCOwwCO5kjNyEzW}
ovn.cnlldfe{QezCrBSMlO6wqSaUVHyokDSq7xG.0FM0MDOxvCO4kjNyEyW}
ovn.college{QezCrBSNlN6wqTaTVHynkDRr7xH.0FM0MDOwwCO5kjMzDzW}
owm.bokkdfd{QezCrBSNkO6vqTaUWHxokDSr7xG.0FM0LDNxvCO5kiMzDzW}
owm.boklege{QdzBqBSMlO6vqTaTWGxokDSr7yH.0FL0LDOxwCN5kjNyEzW}
owm.cnkkdge{QdyCrCRNlO6wqTaTWHxnjDSr6yG.0EL0LDOwvCO4kjMzEzW}
owm.college{QezCrBSNkO6wqTaUWHxokCRr7yH.0FM0MDOwwCN4kjNzEzV}
own.bolkdge{QezCrCSNlO6wqSaTVGyojCSq7yH.0FL0LDNxwCO5kjNzDzW}
own.bolldge{QeyCrCSMkN6wpTaUVHxnjCSr7yG.0FL0LDNwwBO4kjNzEzW}
own.cnlkdge{PdyCrCRNkN5vpTaUVHyokCRr7yH.0EL0LDOxwCN5kjNzEzV}
own.cnllefe{PezCrCSNkO6wpTaTWHyokDSr7yG.0EM0MCOxwCO4kiMyDzW}
own.cnllefe{QdzBrBRNlO5vqSaUWGyokCSr7xH.0FL0MCOxwCO5kjNyEzW}
own.coklegd{QdyCrBSNlN6vpSaUVHyokDSr7yH.0EM0LDOxwCO5kjMzEyW}
own.coklege{PeyCrCRNlO6wqTaUWHynkDRr7yH.0FM0MDOxvCN5kiNzEzV}
own.coklege{QezCrCSNlO6wqTaUWHyojDRr7yG.0FM0MDOwwCO5kjMzEzW}
own.colkege{QdzCrCSNkO6wqTaTWGyojDSr7yH.0FM0LCOxwCO5kjNzDzW}
own.colkege{QeyCrCSNlO6wqTaUWHyokDSr7yH.0FM0MDNxwCO5kjNzEzW}
own.colldge{PezBrCRNlN6vqTaUWHynkCRr7yH.0EL0MDOxwBO4kiNzEzW}
own.college{QezCrBSNlO6wqTaUVHyokDSr7yH.0FM0LDOxwCO5kjNzEzW}
own.college{QezCrCSNlO6vqTaUVHyokDSr7yH.0FL0MDOxwCN5kjNzEzW}
own.college{QezCrCSNlO6wqTaUWHyokDSr7yH.0FM0MDOxwCO5kjNzEzW}
pvm.bollefd{PeyCrCSMlN6vpTaTVHyokDSr6yH.0EM0MDOxwCN4jiNzEzV}
pvm.cnkkege{QeyCrCRMlO6wqTaTWHxnjDRr6yH.0EM0LDNxvCO4kjMyEyW}
pvm.cnllegd{QezCrBSNlO6vqTaTVHyojCSr6yG.0FM0MCNxwCO4kjNzEyW}
pvm.coklefe{QeyCrCRNlO5vqSaTVHxokDRq7xG.0EM0MDNwwCO4jjMyEzW}
pvm.colkege{QezCrCSMlO5wqTaUWHyojDSr6yH.0FM0MDOwwCO5kjNzDzW}
pvn.bnllege{QdzCqCSNlO5wqSaTWHyokDRq7yH.0FM0MDOxvCN5jjMzDyW}
pvn.boklege{QeyCqBSNlO6wpTaUWHyokDSr7yG.0EM0LDNxvBO4jjNzEzW}
pvn.bolldfe{PeyBrBSMlO5vpSaUWGxnjDRr7xH.0EL0MCOwwCO5kiMzEzW}
pvn.bolldfe{QezCqCRMkN6wqTaUWHyokCSq7yH.0FL0MDNxwBN5jiNzDzV}
pvn.bolldgd{QeyCrCSMlN5wpSaUWHyojDSr7yH.0FM0MCOxwCO5kiNyEzV}
pvn.bollege{PeyBqCSMlN6vqSaUVGyojDSr7yH.0EL0MDOxwCO5jjMyDyW}
pvn.cnlkdge{QezBqCRNlO5wpSaTVGyojDRr7yG.0FL0LDNxwBO5jjNzEyW}
pvn.cnlldfe{QdzCqBSNlO6vqSaTWGxnkDSr7xH.0FM0MCOwwCN4kiMyDzV}
pvn.cokkefe{QezBrCSNlO6wqTaUWGxnkDSr7yH.0EL0MDOxvCO5kiNzEzW}
pvn.coklege{PdyCrCRMkO6wqTaUWGyojDSq7yH.0FM0MDOxvCO5kiNzDyW}
pvn.coklege{PezBrCRNkN6wqTaTWHynkDSr7yH.0FL0MDNwvBN4jjNzEzW}
pvn.collefe{QdzCrCSNlO5wqTaTWHyojDSr7yH.0FL0MDOxwCN5kjNzEzW}
pvn.collegd{PezBrCSNkN6vqSaTWHxnkCSr6yH.0FM0MCOxvBN4kiMzEzW}
pvn.collegd{QezCrBSNlO5wqTaUVHyokCSq7yH.0FM0MDOwwCO5kjNyEzW}
pvn.college{QezCrCRNkN6wqTaUWHyokDSr7yG.0FM0MDNxwCO4kjNzEzW}
pwm.bnkldge{PdzBqBSNkO5wpSaUWHxnkDSq6xH.0FM0MDOwvCN5kjMzEzW}
pwm.bnlkege{PeyCrCSNkN5wpSaUWHxojDSr6yG.0FM0MCOwvCN4kjNzDyW}
pwm.bokkege{PezCrBRMlO6wqTaUWHxokDSr7yH.0FM0MDOxvCO4jjNzEzW}
pwm.bolkdge{QezCqBSNkN6wqTaUVGyokDSq7xH.0EM0LDOwwBN5kiNzEyW}
pwm.bolldge{PezBrCRMlO5vpTaTWHxojCRr7xH.0FM0LCOxwBO5kjNzEyV}
pwm.bollegd{QezCrCSMlO6wqTaTWHyojDSr7yH.0FM0MCOxwBO5kiNzEzW}
pwm.cnkkege{QdzCrCRNlO6wqSaUWHyokCRr7yH.0EM0MDOxwBO5kjNzEzV}
pwm.cnklegd{QezCrCSMkO6wqTaTVGyokDSr7xH.0FM0MDNxwCO5kjNzEzW}
pwm.cnlkefe{QezCrCSNlO6wpTaUVHyokDSr7yG.0FL0MDOwwCN5kjMyDzW}
pwm.cnllege{QdzCqBRNkN5vpTaUWGynjCRr7yH.0FM0MDNwwBO5kjNyEzW}
pwm.cokkdge{QdzCrCSNlO6wpTaUVHxokDSr6yH.0FM0LDOxwCO5kjNzDyW}
pwm.colldfd{QdzCrBSNlO6wpSaUWHyokDSr7yG.0FM0LDOxwCO4kjNyEyW}
pwm.colldge{QdyCrCRNlO5vqSaTVHyojDSr7xG.0FM0MCOxwCO5kjNzEzW}
pwm.college{PdzCrBRNlO5wqSaTWHxnkDSr6yH.0FM0LCOxvCO5kjNyDzW}
pwm.college{QdyBrCSMkN5wqTaUWHyokDSr7yH.0EM0MDNxwBO5kjNyEyV}
pwm.college{QdzBrCSNlO6wqTaUVHynkDSr7yH.0FM0MCNxwCN5kjMzDzW}
pwm.college{QdzCrCSNlN6wqTaUWHyokCSr7yH.0FM0MDOxwCO5kjNzEzW}
pwm.college{QezCrCSNkO6vqTaUWHxokDRr7yH.0FM0MDOxwCO5kjNzEzW}
pwm.college{QezCrCSNlO5vqTaUWHynkCSq7yH.0FM0MCOxwBN5jjNzEzW}
pwn.bokkdgd{QdyBrBSNkO5wqSaTVHyokCSq7yH.0FM0MDOxvBO4kjNzDzW}
pwn.bokkegd{QdyCqCSMlO6wpTaUWGxnkCSr7yH.0EL0MDNwvBO5jiNzDyV}
pwn.boklegd{PeyCrBSNlO6wqSaUWHxnkDSr6yG.0FL0MCOxwBO5kjMzEzV}
pwn.bolldge{QezBrCSMlO6vqTaTWHyokDRq6yH.0EM0LDOxwCN5kjMyEyW}
pwn.bollegd{QezCqBSMlO6wqTaTVHynkDSr7yH.0FL0MDNxwBO5kjNyDzV}
pwn.bollege{QezCrCSNlO6wpTaUVHyokDSr7yH.0FM0MCOxwCO5jjNzEzW}
pwn.cnklegd{QezCrCSMlN6vqTaTWGxnkDRr7xH.0FM0MDNxwCO5jjMzDyV}
pwn.cnklege{QdzCrCSNlO6wqTaUWHxojDSq6yH.0EM0MDOxwCN5jjNzEzW}
pwn.cnlldfe{QdzCqCSNlO6vqSaUVGyokDSq6yG.0FL0LCNwwCO5kjMyEzW}
pwn.cnllefd{QezCrCSNlO6vpTaUWHyokDSq7yH.0FM0MDNxwCN5kjMzEzV}
pwn.cnllefe{QdzBrCSMlO6wqTaUWHyokDSr7yH.0FM0MDOxwBO5kiMzEzW}
pwn.cnllegd{QeyCrCSNkO6wpSaUWGyokDSr7yH.0FM0MDOxwCO5kjNzEzW}
pwn.cnllege{QezCrCSNkO6wpTaUWGyokDRq7yH.0FL0LDOxwCO5kiNyEzV}
pwn.cnllege{QezCrCSNlO6wqTaUWHynjDRq7yH.0FM0MDNxvCO5kjNzEzW}
pwn.coklege{QezCqCSNlO6wqTaUWGyokDSr7yH.0EM0MDOxwBO5jjMzEzW}
pwn.colkegd{QezCrCSNkN6vpTaUVHyokDSr7yG.0FM0MDOwwCN5kiMyEzW}
pwn.colldfe{QezBrBSNlN6wqTaTWHyokDRr7yH.0EM0MDOwvCO4kiMzDzW}
pwn.colldge{QdyBrCSMkO5wpSaUWHyokCSq6yH.0EM0MDOxvCO5kjMyEyW}
pwn.colldge{QezBrCSNlO6wpTaUWHyokDSr7xG.0FM0MDOxwCN5kjNzEzW}
pwn.colldge{QezCrCSNlO6wqTaUWHyokDSr7yH.0FM0MDOxwCO5kjNzEzW}
pwn.collefd{PezCrCSNlO6wqTaUWHxojDSr7yH.0FL0MDOxwCN5kjNzEzW}
pwn.collefe{QezCrCSNlO6wqTaUWHyokDSr7yH.0FM0MDOxwCO5jiNzEzW}
pwn.college{PezCrCSMkO6wqSaTWHynkDRq6xG.0EM0LCOwwCO5kiNyDyW}
pwn.college{PezCrCSNlO6wpTaUWHyokDSr7yH.0FM0MDNxwCO5kiNzEzW}
pwn.college{QdzBrCSNlO6wqTaUWHynjDSq6yH.0EM0MDNwwBN5jjNyDyW}
pwn.college{QdzCrCSNkO5vqSaUWHyokDSr7yG.0FM0MDOxwCO4kjNzEzW}
pwn.college{QezBrBSNlN6vqTaUWHynkDSr7yG.0EL0MCOxwCO5jjNzEzW}
pwn.college{QezBrCSNlO6wqTaUWHyokDSr6yH.0FM0LCOxwCO5kjNzDzW}
pwn.college{QezCqCSNlO5wqTaTWHyokCRr7yH.0FM0MDOwwCO5kjMzEzW}
pwn.college{QezCqCSNlO6wqTaUWHyokDSr7yH.0FM0MDOxwCO5kjNzEzW}
pwn.college{QezCrBSNkO6wqTaUWHyokDSr6yH.0FM0MDOxwCO5kjNzDzW}
pwn.college{QezCrCRNlO6wqTaUWHxokDSr7yH.0FM0MDOxwCO5kjNzEzW}
pwn.college{QezCrCSMlO5wqTaUWGyojDSr7yH.0EL0MDNxwCO5kjNzEzW}
pwn.college{QezCrCSNlO6wpTaUVHynkDSq7yH.0FM0LDOxwCN5kjNyEzW}
pwn.college{QezCrCSNlO6wqTaTWHyokDSr7yH.0EM0MDOxwCO5kjNyEzW}
pwn.college{QezCrCSNlO6wqTaUWGyokDRr7yH.0FL0MDOxwCO5kjMyEzW}
pwn.college{QezCrCSNlO6wqTaUWHyokDSq7yH.0FM0MDOxvCO5kjMzEzV}
pwn.college{QezCrCSNlO6wqTaUWHyokDSr7yG.0FM0MDOxwCO5kjNzEzW}
pwn.college{QezCrCSNlO6wqTaUWHyokDSr7yH.0FM0MDOxwCO5kjNzEzW}
hacker@data~sorting-data:~$
```
In this challenge, I simply ran sort /challenge/flags.txt that sorted the 101 flags alphabetically(as it does by default
if no argument is specified) and the last flag printed is the real flag.
### What I learned
Files (or output lines of commands) aren't always in the order we need them! The sort command helps us organize data. It reads lines from input (or files) and outputs them in sorted order
By default, sort orders lines alphabetically. Arguments can change this:

-r: reverse order (Z to A)
-n: numeric sort (for numbers)
-u: unique lines only (remove duplicates)
-R: random order!
### References
Instructions in pwn.college website.























