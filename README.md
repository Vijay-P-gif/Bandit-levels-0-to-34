## Level 0 
The command used is ssh bandit0@bandit.labs.overthewire.org -p 2220. THE  PASSWORD IS bandit0
After accepting the host key and entering the password, access to the Bandit shell is granted.
This level teaches the basics of SSH, remote login, and terminal authentication.
It prepares the player for navigating files and commands in later levels.
<img width="1647" height="1043" alt="Screenshot 2026-01-30 172752" src="https://github.com/user-attachments/assets/46c5411d-b47b-4892-b901-eac93c58e6b6" />


### Password:bandit0

## Level 0 to 1
 
In this level, the goal is to find the password for bandit1 after logging in as bandit0 using SSH.
After login, listing  files with is shows a file named readme in the home directory. Using the command cat readme displays the contents of the file.
Inside the file is the password for the next level  is ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
This level teaches basic Linux commands like ls and cat.
### Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
<img width="1535" height="1097" alt="Screenshot 2026-01-30 173111" src="https://github.com/user-attachments/assets/3cd001eb-1c7f-410b-9faa-09846cf106fd" />


## Level 1 to 2
 
In this level, the password for bandit1 is stored in a file named - in the home directory.
Because - is treated as an option in Linux commands, a normal cat - will not work.
To read it, you must specify the path explicitly using cat ./-.
This displays the password for the next level.
The level teaches how to handle special filenames in Linux.
It introduces the use of ./ to correctly reference files with unusual names
### Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx 
<img width="1535" height="1097" alt="Screenshot 2026-01-30 173111" src="https://github.com/user-attachments/assets/0e747062-3c56-4c81-a809-42788f00af4f" />

## Level 2 to 3
 
In this level, the password for bandit3 is stored in a file whose name contains spaces
Using a normal cat filename fails because the shell treats spaces as separators.
You must either escape spaces with backslashes or use quotes .This reveals the next password.
The level teaches how to handle filenames with spaces in Linux.
### Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
<img width="1486" height="640" alt="Screenshot 2026-01-30 174237" src="https://github.com/user-attachments/assets/edae231e-cde9-4d1d-8936-27f4ac6d7eb3" />


## Level 3 to 4
 
In this level, the password for bandit4 is hidden inside a directory named inhere.
After logging in, use ls and cd inhere to enter the directory.
The file is hidden (starts with a dot), so it will not appear with normal ls.
Use ls -a to show hidden files, then read it with cat .hidden.
This reveals the next password.
### Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
<img width="1919" height="1199" alt="Screenshot 2026-01-30 181426" src="https://github.com/user-attachments/assets/dc2e20cb-280c-4c47-b246-7412cb3c8ce2" />

## Level 4 to 5
 
In this level, the password for bandit5 is inside the inhere directory among many files.
Most files are binary or unreadable, so you must identify the correct one.Use the file * command to check each file’s type.
Look for the file labelled  ASCII text and open it with cat filename .That file contains the next password. This level teaches how to identify file types using the file command.
### Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
<img width="1919" height="1199" alt="Screenshot 2026-01-30 182036" src="https://github.com/user-attachments/assets/46467a0a-0c21-4839-8709-b2047da690d4" />








## Level 5 to 6
 
In this level, the password for bandit6 is hidden somewhere inside the inhere directory.
The correct file has specific properties: human-readable, 1033 bytes, and not executable.
Use the find command with conditions to search, e.g.find . -type f -size 1033c !  executable.
After locating the file, open it with cat to reveal the password.
This level teaches advanced file searching with the find command.
### Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
<img width="1919" height="1199" alt="Screenshot 2026-01-30 182522" src="https://github.com/user-attachments/assets/01f054b3-3c70-43af-ab86-b78b97837a52" />

## Level 6 to 7
 
In this level, the password for bandit7 is stored somewhere on the server with specific conditions.
The file is owned by user bandit7, group bandit6, and 33 bytes in size.
Use the find command from root with filters, e.g.find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null.
Open the located file using cat to get the password.
### Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
<img width="1919" height="1199" alt="Screenshot 2026-01-30 190312" src="https://github.com/user-attachments/assets/c7a88cfa-ed8c-44ab-b1f4-3667a3c8a039" />

## Level 7 to 8
 
In this level, the password for bandit8 is stored in a file named data.txt.
The file contains many lines, but only one line includes the word “millionth.”
Use the grep command to search for that keyword, e.g.
grep millionth data.txt.
The line that appears contains the next password.
This level teaches basic text searching using the grep command in Linux.
### Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
<img width="1914" height="1187" alt="Screenshot 2026-01-30 190821" src="https://github.com/user-attachments/assets/f7995067-476c-430a-a54d-d8e5fa3fca8e" />









## Level 8 to 9
 
In this level, the password for bandit9 is stored in data.txt.
The correct password is the only line that appears once in the file.
First sort the file, then find unique lines using:
sort data.txt | uniq -u
The output will show the single non-repeating line, which is the next password.
This level teaches how to combine sort and uniq to find unique data.
### Password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
<img width="1919" height="1199" alt="Screenshot 2026-01-30 191831" src="https://github.com/user-attachments/assets/0d095660-cb97-4b30-90c7-7e6a2e27a74d" />









## Level 9 to 10
 
In this level, the password for bandit10 is hidden inside data.txt among many binary and special characters.
The password is located next to several “=” symbols.
Use the strings command to extract readable text from the file.
Then filter it using: strings data.txt | grep "="
Among the results, you will find the correct password line.
This level teaches how to extract human-readable strings from binary files.

### Password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
<img width="1918" height="1197" alt="Screenshot 2026-01-30 200409" src="https://github.com/user-attachments/assets/7c89d284-2740-49a8-b645-09109ecedc21" />







## Level 10 to 11
 
In this level, the password for bandit11 is stored in data.txt, but it is Base64 encoded.
You need to decode it to get the real password.
Use the command: base64 -d data.txt
The decoded output will directly show the next password.
This level teaches how to recognize and decode Base64-encoded data in Linux.
### Password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
<img width="1919" height="1199" alt="Screenshot 2026-01-30 200845" src="https://github.com/user-attachments/assets/6e51b93d-6601-4e5b-a011-13f38a6fa7e6" />








## Level 11 to 12
 
In this level, the password for bandit12 is stored in data.txt, but it is encrypted using a ROT13 cipher.
You must rotate each letter by 13 positions to reveal the real text.
Use the tr command:
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The output will display the correct password.
This level teaches simple character substitution and basic text transformation in Linux.
### Password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
<img width="1919" height="1199" alt="Screenshot 2026-01-30 203407" src="https://github.com/user-attachments/assets/b61c9b35-0590-41c8-b1f5-791c650bc685" />









## Level 12 to 13
 
 
In this level, the password for bandit13 is hidden inside data.txt, which is a hex dump of a compressed file.
First reverse the hex using xxd -r data.txt > data.
Then repeatedly use file to identify formats and decompress them (gzip -d, bzip2 -d, tar xf).
The file is nested multiple times, so you must keep extracting layer by layer.
Eventually a plain text file appears containing the password.
This level teaches file identification and handling multiple compression formats in Linux.
### Password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
<img width="1919" height="1199" alt="Screenshot 2026-01-31 104510" src="https://github.com/user-attachments/assets/858b4556-b500-4003-aaa8-a7d6f281cff8" />





## Level 13 to 14 
In this level, the password for bandit14 is not in a text file but accessed using an SSH private key.
Inside bandit13’s home directory, there is a file named sshkey.private.Use it to log in as bandit14 with: ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
After logging in, read /etc/bandit_pass/bandit14 to get the password.
This level teaches SSH key-based authentication instead of passwords.
### Password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
<img width="1919" height="1199" alt="Screenshot 2026-01-31 120646" src="https://github.com/user-attachments/assets/16aeb7fb-e9cb-4611-bee9-0c18ac330b14" />










## Level 14 to 15
 
 
In this level, the password for bandit15 is obtained by sending the current password to a local network service.
Use the command: nc localhost 30000 to connect to the port.
After connecting, paste the bandit14 password and press Enter.
The service will respond with the next password.
This level teaches basic networking using netcat (nc) to communicate with services.
### Password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
<img width="1919" height="1199" alt="Screenshot 2026-01-31 120925" src="https://github.com/user-attachments/assets/0d35eb05-3f8b-4993-a143-00342f2540ec" />



## Level 15 to 16
 
In this level, the password for bandit16 is retrieved through an SSL encrypted connection.
Use OpenSSL to connect to the local service on port 30001:
openssl s_client -connect localhost:30001
After the SSL connection is established, paste the bandit15 password.
The server replies with the next password.
This level teaches how to use OpenSSL to communicate with secure services.
### Password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
<img width="1919" height="1199" alt="Screenshot 2026-01-31 121302" src="https://github.com/user-attachments/assets/4feac2af-cec4-4093-a2ef-64a90d9f0713" />


## Level 16 to 17
In this level, the password is obtained by finding the correct SSL service port.
First scan ports 31000–32000 using nmap localhost -p 31000-32000 to find which port supports SSL.
Then connect to the valid port using: openssl s_client -connect localhost:<port>.
Paste the bandit16 password and the service returns an SSH private key.
Save this key to a file, set permission chmod 600, and SSH into bandit17.
This level teaches port scanning and using SSL services to retrieve credentials.




## Level 17 to 18
 
In this level, the password for bandit18 is found by comparing two files: passwords.old and passwords.new.Both files are in the home directory of bandit17.
Use the command: diff passwords.old passwords.new.
The line that is different in passwords.new is the next password.
This level teaches how to compare files and spot changes using the diff command in Linux.
### Password: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
<img width="1919" height="1199" alt="Screenshot 2026-01-31 125830" src="https://github.com/user-attachments/assets/2afa2f6d-c5b9-4962-ab60-fb63f6ba7110" />









## Level 18 to 19
 
The password is stored in a file, but normal login immediately logs out.
Use SSH with a command option: ssh bandit18@... -p 2220 cat readme.
This bypasses the logout and shows the next password. 

### Password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
<img width="1919" height="1113" alt="Screenshot 2026-01-31 130129" src="https://github.com/user-attachments/assets/a2acaedd-3a4e-42df-876b-56894e0dc441" />


## level 19 to 20
 
A special binary named bandit20-do runs commands as bandit20.
Execute: ./bandit20-do cat /etc/bandit_pass/bandit20.
The output is the next password.
### Password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
<img width="1919" height="1199" alt="Screenshot 2026-01-31 130500" src="https://github.com/user-attachments/assets/e7ff25fa-e5ed-4460-a6d7-5e117999973f" />


## Level 20 to 21
  
A program suconnect sends the password through a local port.
Open a listener with nc -l -p 4444, then run ./suconnect 4444.
It returns the next password.
### Password: EeoULMCra2q0dSkYj561DX7s1CpBuOBt
<img width="1919" height="1199" alt="Screenshot 2026-01-31 130956" src="https://github.com/user-attachments/assets/7bdcf6cf-bb2b-4dbe-a8fd-4f7731fd7915" />









## Level 21 to 22
 
A cron job runs every minute and copies the password to /tmp.
Check /etc/cron.d and view the related script.
Read the file path shown in the script to get the password.
### Password: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
<img width="1919" height="1132" alt="Screenshot 2026-01-31 131751" src="https://github.com/user-attachments/assets/5111a6ea-cc97-4fdb-8530-77f58fd5abb2" />


## Level 22 to 23
 
Another cron job hashes the username to create a filename.
Generate the same hash using echo "I am user bandit23" | md5sum.
Read /tmp/<hash> to obtain the password.
### Password: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
<img width="1919" height="1131" alt="Screenshot 2026-01-31 132101" src="https://github.com/user-attachments/assets/88370fe2-909e-4f91-814d-9866a2e32c0d" />



## Level 23 to 24
 
Another cron job hashes the username to create a filename.
Generate the same hash using echo "I am user bandit23" | md5sum.
Read /tmp/<hash> to obtain the password.

### Password: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
<img width="1919" height="1127" alt="Screenshot 2026-01-31 133152" src="https://github.com/user-attachments/assets/7171f5e3-55d8-450a-ad64-b51a446bb5a8" />




## Level 24 to 25
 
A service requires the password plus a 4-digit PIN.
Write a brute-force script using nc localhost 30002.
When the correct PIN hits, the server reveals the password.

### Password: iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
<img width="1919" height="1104" alt="Screenshot 2026-01-31 133518" src="https://github.com/user-attachments/assets/54898c87-afbd-4221-b6cb-bd088a553489" />


## Level 25 to 26
 
Login uses a limited shell that opens more.
Resize the terminal small and escape into vim using v.
From vim, open a shell and read the password.And it went through the bandit 26 shell 
<img width="1919" height="1122" alt="Screenshot 2026-01-31 141937" src="https://github.com/user-attachments/assets/1573c317-61ae-4f39-8b06-ce1f96752b61" />










## Level 26 to 27
 
A binary bandit27-do runs commands as bandit27.
Execute: ./bandit27-do cat /etc/bandit_pass/bandit27.
This prints the next password.
### Password: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
<img width="1919" height="1103" alt="Screenshot 2026-01-31 144356" src="https://github.com/user-attachments/assets/62003428-c6fd-477b-b609-592b71480591" />



## Level 27 to 28
 
Use git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/....
Enter the bandit27 password when prompted.
Inside the repo, check files like README.md.
The password is stored directly in the repository.

### Password: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
<img width="1919" height="1158" alt="Screenshot 2026-01-31 144559" src="https://github.com/user-attachments/assets/39f69dbf-0a07-45fa-b825-003d618fb0ba" />


## Level 28 to 29
 
The current README hides the password with Xs.
Use git log to view commit history.
Checkout an older commit using git checkout <id>.
The previous version reveals the real password.
This level teaches Git history inspection.

### Password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
<img width="1919" height="1151" alt="Screenshot 2026-01-31 145202" src="https://github.com/user-attachments/assets/aca136bc-9444-456d-91ba-bbc64bf955ab" />







## Level 29 to 30
 
The password is not on the main branch.List all branches using git branch -a.Switch to the dev branch with git checkout dev.Open the README or related files.
The password is stored there.
### Password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
<img width="1919" height="1122" alt="Screenshot 2026-01-31 161909" src="https://github.com/user-attachments/assets/b8275440-387b-44a6-998c-78d0ece728fa" />


## Level 30 to 31
 
The repository appears empty of passwords.Check Git tags using git tag.
View tag details with git show <tagname>. Which is no password pritection
One tag message contains the password. And opening the Readme md file to find password
This teaches exploring Git metadata.

### Password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
<img width="1919" height="1135" alt="Screenshot 2026-01-31 162403" src="https://github.com/user-attachments/assets/0ddea036-cca7-4d40-8253-d2348bffa52e" />



## Level 31 to 32
 
The repository appears empty of passwords.
Check Git tags using git tag. And the git tag is secret which is a text file
One tag message contains the password.
This teaches exploring Git metadata.

### Password: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
<img width="1919" height="1132" alt="Screenshot 2026-01-31 163259" src="https://github.com/user-attachments/assets/e4d2f18e-0720-451c-bd0f-684c6315d5ee" />










## Level 32 to 33
 

You enter an uppercase-only shell.Normal commands fail because input is forced uppercase.
Type $0 to start a normal shell.Now standard Linux commands work.
Read /etc/bandit_pass/bandit33 for the password.

### Password: tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
<img width="1919" height="1199" alt="Screenshot 2026-01-31 165743" src="https://github.com/user-attachments/assets/dc824452-6d84-4be4-b928-b8dfb3b8b049" />









## Level 33 to 34
 
This is the final level of Bandit. There is no new password to retrieve.
A README file congratulates you for finishing.
It suggests trying other Over The Wire games.
The Bandit wargame officially ends here.
<img width="1919" height="1199" alt="Screenshot 2026-01-31 170343" src="https://github.com/user-attachments/assets/81f337ca-fc62-4197-af99-79e66d937843" />




















