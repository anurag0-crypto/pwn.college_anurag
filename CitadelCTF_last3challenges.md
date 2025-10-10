# Selected Ambient Work
This CTF challenge asks to analyze the sound file to reveal its secret message.
### My Solve
I was not able to solve the challenge fully but was able to guide my team to the correct direction.
I used a tool called sonic visualiser to display the frequencies of the sound file.
Within 1:03 to 1:13 of the sound file, there was written : citadel{           }  , in the spectogram
<img width="1271" height="797" alt="image" src="https://github.com/user-attachments/assets/0b573cb4-0302-4234-b87e-2c58efecf551" />

I set the colour black and white and window as 4096 to try to view the hidden text in the flag.

In the midst of doing this, my teammate submitted the flag and completed the challenge successfully.
### What I learned
I learned to use Sonic Visualiser, a powerful, free tool for audio analysis. It's the standard for this kind of forensic audio work.
### References
Sonic Visualiser and the web browser.


# Robot's Trail
A guardian robot leaves a trail in a virtual maze. If its path is followed it leads to discover the key.
Initial URL provided: https://therobotstrail.citadel.cryptonitemit.in
### My Solve
Flag: citadel{p4th_tr4v3rs4l_m4st3ry_4ch13v3d}
 I Started by checking robots.txt. I found:
<img width="1250" height="300" alt="image" src="https://github.com/user-attachments/assets/3f053aea-0d12-4e1c-bcc7-87a847c438e7" />


This revealed:

A /file endpoint exists
It's vulnerable to path traversal via path parameter
The server runs on Linux (references to /etc/passwd)

Then, I accessed /file?path=../../etc/passwd and found an interesting entry in webadmin user's GECOS field:
<img width="1251" height="157" alt="image" src="https://github.com/user-attachments/assets/bac57fc7-d752-4260-9abe-51f8d1ba77ed" />

Then I accessed: /file?path=../../var/www/html/config.php and found database credentials and a new hint:
<img width="1253" height="173" alt="image" src="https://github.com/user-attachments/assets/102cffbf-326f-4d9a-82d9-4d644b200d11" />
<img width="1245" height="393" alt="image" src="https://github.com/user-attachments/assets/fe6f6c5b-c769-4df3-bc73-cd5205c9a93a" />

Then, I accessed /file?path=../../var/log/apache2/access.log and found a comment hidden in the logs
<img width="1252" height="137" alt="image" src="https://github.com/user-attachments/assets/f267b843-cd65-413b-b479-53130e7558f6" />

Then, I checked https://therobotstrail.citadel.cryptonitemit.in/file?path=../../proc/self/environ as /proc/self/environ contains the environment variables of the current process (the web server).
In CTFs, this often contains the flag if it was passed as an environment variable.
<img width="1248" height="344" alt="image" src="https://github.com/user-attachments/assets/2bdd3e17-afde-423c-bdb1-811076724447" />

Then, I tried to access the secret file via the url https://therobotstrail.citadel.cryptonitemit.in/file?path=../../home/ctf/.secret and found:
<img width="1241" height="355" alt="image" src="https://github.com/user-attachments/assets/d714b179-bdfb-4524-b927-d7beb8a7d73b" />

Here, we see a directory listing for /home/ctf/.secret showing flag.txt is inside.
Finally, I retrieved the flag using the url https://therobotstrail.citadel.cryptonitemit.in/file?path=../../home/ctf/.secret/flag.txt

### What I learned
robots.txt as an Information Source: Often contains hidden endpoints or disallowed paths that reveal application structure

Path Traversal Attacks: Unfiltered ../ sequences can expose sensitive files

Linux File System Forensics:

/etc/passwd contains user information and sometimes hints

/proc/self/environ reveals process environment variables

Log files can contain hidden messages or clues

Progressive Hint Chains: CTF challenges often use a breadcrumb trail where each step reveals the next location
### References
The web browser(for basic navigation)
OWASP Path Traversal Prevention: https://owasp.org/www-community/attacks/Path_Traversal


# Coco Conjecture
The challenge required implementing the Collatz conjecture (3n+1 problem) for very large numbers (up to 10¹⁸) in real-time against a server. 
After connecting, the server would send 269 numbers sequentially, and for each number, we had to compute how many steps it takes to reach 1 using the Collatz rules, responding within 0.5 seconds per calculation.
### My Solve
Flag: Cannot be accessed anymore because the challenge ended and I did not save the flag.
Step 1: Understanding the Collatz Conjecture
The rules are straightforward:

If n is even: n = n / 2

If n is odd: n = 3n + 1
Count steps until reaching 1, where steps(1) = 0.

Step 2: Implementation Strategy
I used Python with memoization for efficiency since numbers could be as large as 10¹⁸. The key insight was that many numbers share common subsequences in their Collatz paths, so caching results dramatically improved performance.
Step 3: Network Communication
The server communication had two phases:

Initial test numbers: Simple numbers (1, 5, 269) to verify basic functionality

Main rounds: 269 problems in format "Round X: [large number]"

I used Python's socket library to handle the TCP connection, parsing server messages and extracting numbers using regex to handle the "Round X: NUMBER" format.
I ran this script 

import socket
import re

# Memoization cache for efficiency
memo = {}

def collatz_steps(n):
    """Calculate steps for Collatz conjecture with memoization"""
    if n == 1:
        return 0
    if n in memo:
        return memo[n]
    
    if n % 2 == 0:
        steps = 1 + collatz_steps(n // 2)
    else:
        steps = 1 + collatz_steps(3 * n + 1)
    
    memo[n] = steps
    return steps

def solve_challenge():
    # Connect to the server
    host = 'chall_citadel.cryptonitemit.in'
    port = 61234
    
    print(f"Connecting to {host}:{port}")
    
    try:
        # Create socket connection
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(30)
        sock.connect((host, port))
        
        buffer = b""
        round_count = 0
        
        while True:
            # Receive data
            try:
                data = sock.recv(1024)
                if not data:
                    print("Connection closed by server")
                    break
                    
                buffer += data
                
                # Process complete lines
                while b'\n' in buffer:
                    line, buffer = buffer.split(b'\n', 1)
                    line = line.decode().strip()
                    
                    if not line:
                        continue
                        
                    print(f"Received: {line}")
                    
                    # Check for flag
                    if 'citadel{' in line:
                        print(f"\n🎉 FLAG FOUND: {line} 🎉")
                        return line
                    
                    # Check if this is a round with format "Round X: NUMBER"
                    if 'Round' in line and ':' in line:
                        numbers = re.findall(r'\d+', line)
                        if len(numbers) >= 2:
                            n = int(numbers[-1])  # The actual number to process
                            round_count += 1
                            result = collatz_steps(n)
                            print(f"Round {round_count}: n={n} -> steps={result}")
                            
                            response = f"{result}\n"
                            sock.sendall(response.encode())
                            print(f"Sent: {response.strip()}")
                        continue
                    
                    # Check if it's just a plain number (initial tests)
                    numbers = re.findall(r'^\d+$', line)  # Only match if entire line is a number
                    if numbers:
                        n = int(numbers[0])
                        result = collatz_steps(n)
                        print(f"Test: n={n} -> steps={result}")
                        
                        response = f"{result}\n"
                        sock.sendall(response.encode())
                        print(f"Sent: {response.strip()}")
                        
            except socket.timeout:
                print("Timeout - no data received")
                break
            except Exception as e:
                print(f"Error: {e}")
                break
                
    except Exception as e:
        print(f"Connection error: {e}")
    finally:
        sock.close()
        print("Connection closed")

# Run the solution
if __name__ == "__main__":
    result = solve_challenge()
    if result:
        print(f"\nFinal result: {result}")



        





After correctly answering all 269 problems, the server returned the flag.
### What I learned
Memoization is crucial for mathematical sequences with overlapping subproblems

Network protocol parsing requires careful handling of different message formats

The Collatz conjecture remains unsolved mathematically but is computationally tractable for individual numbers

Time constraints (0.5s per calculation) necessitate optimized algorithms
### References
Collatz Conjecture (Wikipedia)
Python socket programming documentation
Competitive programming memoization techniques





