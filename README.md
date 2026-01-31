Level 0 
The command used is ssh bandit0@bandit.labs.overthewire.org -p 2220. THE PASSWORS IS bandit0
After accepting the host key and entering the password, access to the Bandit shell is granted.
This level teaches the basics of SSH, remote login, and terminal authentication.
It prepares the player for navigating files and commands in later levels.
<img width="1647" height="1043" alt="Screenshot 2026-01-30 172752" src="https://github.com/user-attachments/assets/46c5411d-b47b-4892-b901-eac93c58e6b6" />


Password:bandit0
Level 0 to 1
 
In this level, the goal is to find the password for bandit1 after logging in as bandit0 using SSH.
After login, listing  files with is shows a file named readme in the home directory. Using the command cat readme displays the contents of the file.
Inside the file is the password for the next level  is ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
This level teaches basic Linux commands like ls and cat.
Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
<img width="1535" height="1097" alt="Screenshot 2026-01-30 173111" src="https://github.com/user-attachments/assets/3cd001eb-1c7f-410b-9faa-09846cf106fd" />


Level1 to 2
 
In this level, the password for bandit1 is stored in a file named - in the home directory.
Because - is treated as an option in Linux commands, a normal cat - will not work.
To read it, you must specify the path explicitly using cat ./-.
This displays the password for the next level.
The level teaches how to handle special filenames in Linux.
It introduces the use of ./ to correctly reference files with unusual names
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx 






Level 2 to 3
 
In this level, the password for bandit3 is stored in a file whose name contains spaces
Using a normal cat filename fails because the shell treats spaces as separators.
You must either escape spaces with backslashes or use quotes .This reveals the next password.
The level teaches how to handle filenames with spaces in Linux.
Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
Level 3 to 4
 
In this level, the password for bandit4 is hidden inside a directory named inhere.
After logging in, use ls and cd inhere to enter the directory.
The file is hidden (starts with a dot), so it will not appear with normal ls.
Use ls -a to show hidden files, then read it with cat .hidden.
This reveals the next password.
Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
Level 4 to 5
 
In this level, the password for bandit5 is inside the inhere directory among many files.
Most files are binary or unreadable, so you must identify the correct one.Use the file * command to check each file’s type.
Look for the file labelled  ASCII text and open it with cat filename .That file contains the next password. This level teaches how to identify file types using the file command.
Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw






Level 5 to 6
 
In this level, the password for bandit6 is hidden somewhere inside the inhere directory.
The correct file has specific properties: human-readable, 1033 bytes, and not executable.
Use the find command with conditions to search, e.g.find . -type f -size 1033c !  executable.
After locating the file, open it with cat to reveal the password.
This level teaches advanced file searching with the find command.
Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
Level 6 to 7
 
In this level, the password for bandit7 is stored somewhere on the server with specific conditions.
The file is owned by user bandit7, group bandit6, and 33 bytes in size.
Use the find command from root with filters, e.g.find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null.
Open the located file using cat to get the password.
Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
Level 7 to 8
 
In this level, the password for bandit8 is stored in a file named data.txt.
The file contains many lines, but only one line includes the word “millionth.”
Use the grep command to search for that keyword, e.g.
grep millionth data.txt.
The line that appears contains the next password.
This level teaches basic text searching using the grep command in Linux.
Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc








Level 8 to 9
 
In this level, the password for bandit9 is stored in data.txt.
The correct password is the only line that appears once in the file.
First sort the file, then find unique lines using:
sort data.txt | uniq -u
The output will show the single non-repeating line, which is the next password.
This level teaches how to combine sort and uniq to find unique data.
Password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM








Level 9 to 10
 
In this level, the password for bandit10 is hidden inside data.txt among many binary and special characters.
The password is located next to several “=” symbols.
Use the strings command to extract readable text from the file.
Then filter it using: strings data.txt | grep "="
Among the results, you will find the correct password line.
This level teaches how to extract human-readable strings from binary files.
Password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey







Level 10 to 11
 
In this level, the password for bandit11 is stored in data.txt, but it is Base64 encoded.
You need to decode it to get the real password.
Use the command: base64 -d data.txt
The decoded output will directly show the next password.
This level teaches how to recognize and decode Base64-encoded data in Linux.
Password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr








Level 11 to 12
 
In this level, the password for bandit12 is stored in data.txt, but it is encrypted using a ROT13 cipher.
You must rotate each letter by 13 positions to reveal the real text.
Use the tr command:
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The output will display the correct password.
This level teaches simple character substitution and basic text transformation in Linux.
Password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4








Level 12 to 13
 
 
In this level, the password for bandit13 is hidden inside data.txt, which is a hex dump of a compressed file.
First reverse the hex using xxd -r data.txt > data.
Then repeatedly use file to identify formats and decompress them (gzip -d, bzip2 -d, tar xf).
The file is nested multiple times, so you must keep extracting layer by layer.
Eventually a plain text file appears containing the password.
This level teaches file identification and handling multiple compression formats in Linux.
Password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
Level 13 to 14 
In this level, the password for bandit14 is not in a text file but accessed using an SSH private key.
Inside bandit13’s home directory, there is a file named sshkey.private.Use it to log in as bandit14 with: ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
After logging in, read /etc/bandit_pass/bandit14 to get the password.
This level teaches SSH key-based authentication instead of passwords.
Password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS









Level 14 to 15
 
 
In this level, the password for bandit15 is obtained by sending the current password to a local network service.
Use the command: nc localhost 30000 to connect to the port.
After connecting, paste the bandit14 password and press Enter.
The service will respond with the next password.
This level teaches basic networking using netcat (nc) to communicate with services.
Password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo


Level 15 to 16
 
In this level, the password for bandit16 is retrieved through an SSL encrypted connection.
Use OpenSSL to connect to the local service on port 30001:
openssl s_client -connect localhost:30001
After the SSL connection is established, paste the bandit15 password.
The server replies with the next password.
This level teaches how to use OpenSSL to communicate with secure services.
Password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
Level 16 to 17
In this level, the password is obtained by finding the correct SSL service port.
First scan ports 31000–32000 using nmap localhost -p 31000-32000 to find which port supports SSL.
Then connect to the valid port using: openssl s_client -connect localhost:<port>.
Paste the bandit16 password and the service returns an SSH private key.
Save this key to a file, set permission chmod 600, and SSH into bandit17.
This level teaches port scanning and using SSL services to retrieve credentials.





Level 17 to 18
 
In this level, the password for bandit18 is found by comparing two files: passwords.old and passwords.new.Both files are in the home directory of bandit17.
Use the command: diff passwords.old passwords.new.
The line that is different in passwords.new is the next password.
This level teaches how to compare files and spot changes using the diff command in Linux.
Password: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO








Level 18 to 19
 
The password is stored in a file, but normal login immediately logs out.
Use SSH with a command option: ssh bandit18@... -p 2220 cat readme.
This bypasses the logout and shows the next password.
Password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
level 19 to 20
 
A special binary named bandit20-do runs commands as bandit20.
Execute: ./bandit20-do cat /etc/bandit_pass/bandit20.
The output is the next password.
Password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Level 20 to 21
  
A program suconnect sends the password through a local port.
Open a listener with nc -l -p 4444, then run ./suconnect 4444.
It returns the next password.
Password: EeoULMCra2q0dSkYj561DX7s1CpBuOBt









Level 21 to 22
 
A cron job runs every minute and copies the password to /tmp.
Check /etc/cron.d and view the related script.
Read the file path shown in the script to get the password.
Password: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
Level 22 to 23
 
Another cron job hashes the username to create a filename.
Generate the same hash using echo "I am user bandit23" | md5sum.
Read /tmp/<hash> to obtain the password.
Password: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
Level 23 to 24
 
Another cron job hashes the username to create a filename.
Generate the same hash using echo "I am user bandit23" | md5sum.
Read /tmp/<hash> to obtain the password.
Password: gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
Level 24 to 25
 
A service requires the password plus a 4-digit PIN.
Write a brute-force script using nc localhost 30002.
When the correct PIN hits, the server reveals the password.
Password: iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
Level 25 to 26
 
Login uses a limited shell that opens more.
Resize the terminal small and escape into vim using v.
From vim, open a shell and read the password.And it went through the bandit 26 shell 










Level 26 to 27
 
A binary bandit27-do runs commands as bandit27.
Execute: ./bandit27-do cat /etc/bandit_pass/bandit27.
This prints the next password.
Password: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
Level 27 to 28
 
Use git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/....
Enter the bandit27 password when prompted.
Inside the repo, check files like README.md.
The password is stored directly in the repository.
Password: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
Level 28 to 29
 
The current README hides the password with Xs.
Use git log to view commit history.
Checkout an older commit using git checkout <id>.
The previous version reveals the real password.
This level teaches Git history inspection.
Password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN







Level 29 to 30
 
The password is not on the main branch.List all branches using git branch -a.Switch to the dev branch with git checkout dev.Open the README or related files.
The password is stored there.
Password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
Level 30 to 31
 
The repository appears empty of passwords.Check Git tags using git tag.
View tag details with git show <tagname>. Which is no password pritection
One tag message contains the password. And opening the Readme md file to find password
This teaches exploring Git metadata.
Password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
Level 31 to 32
 
The repository appears empty of passwords.
Check Git tags using git tag. And the git tag is secret which is a text file
One tag message contains the password.
This teaches exploring Git metadata.
Password: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy









Level 32 to 33
 

You enter an uppercase-only shell.Normal commands fail because input is forced uppercase.
Type $0 to start a normal shell.Now standard Linux commands work.
Read /etc/bandit_pass/bandit33 for the password.
Password: tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0









Level 33 to 34
 
This is the final level of Bandit. There is no new password to retrieve.
A README file congratulates you for finishing.
It suggests trying other Over The Wire games.
The Bandit wargame officially ends here.



















