# Magikarp Ground Mission

**Platform:** picoCTF  
**Category:** General Skills  
**Difficulty:** Easy  

## Description
Do you know how to move between directories and read files in 
the shell? Login via ssh as ctf-player with the password 
8bc606eb1 on the host wily-courier.picoctf.net and port 62232.

## Approach
The challenge tests basic Linux navigation — connecting to a 
remote machine via SSH then using ls, cd, and cat to find 
flag fragments split across three files in different directories.

## Solution

### Step 1 — Connect via SSH
Connected to the remote server using the provided credentials 
and custom port.

```bash
ssh -p 62232 ctf-player@wily-courier.picoctf.net
```

Entered password when prompted: 8bc606eb1

### Step 2 — Find First Flag Fragment
After connecting ran ls to see available files.

```bash
ls
```

Found 1of3.flag.txt and instructions-to-2of3.txt. 
Read the first fragment:

```bash
cat 1of3.flag.txt
```

Output: picoCTF{xxsh_

### Step 3 — Navigate to Root Directory
Followed the instructions file which directed to the 
root directory.

```bash
cd /
ls
```

Found 2of3.flag.txt. Read the second fragment:

```bash
cat 2of3.flag.txt
```

Output: 0ut_0f_//4t3r_

### Step 4 — Navigate to Home Directory
Followed instructions to the home directory.

```bash
cd ~
ls
```

Found 3of3.flag.txt. Read the final fragment:

```bash
cat 3of3.flag.txt
```

Output: 0b24fc4f}

## Commands Used
```bash
ssh -p 62232 ctf-player@wily-courier.picoctf.net
ls
cat 1of3.flag.txt
cd /
cat 2of3.flag.txt
cd ~
cat 3of3.flag.txt
```

## Flag
picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}


## What I Learned
How to connect to a remote Linux server using SSH with a 
custom port, and how to navigate a file system using cd and 
ls to find files split across multiple directories. Also 
learned that SSH key authentication takes priority over 
password authentication by default — had to accept the host 
fingerprint on first connection.
