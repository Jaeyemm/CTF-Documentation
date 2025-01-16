nmap -sV -sC

gobuster dir- u [ip add | url] -w [wordlist file .txt] -x [file js php etc.]

always check headers
X-powered-By: php file

other tool: exploitdb
find / -name flag.txt 2/dev/null

## wfuzz ## 
is a command-line tool used for fuzzing web applications. It allows you to automate the process of discovering hidden directories, files, and parameters on a web server.

wfuzz -c -z file,/usr/share/wordlists/dirb/common.txt --hc 404 http://10.10.10.245/dataFUZZ
