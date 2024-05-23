# ffuf

## Overview

Tools such as ffuf provide us with a handy automated way to fuzz the web application's individual components or a web page. 

## Options

	-fs: filters responses by response size

## Usage

Directory fuzzing

	ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u http://SERVER_IP:PORT/FUZZ

Parameter fuzzing

	ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u http://admin.academy.htb:PORT/admin/admin.php?FUZZ=key -fs xxx

Fuzzing a file inclusion on windows

	ffuf -w /usr/share/wordlists/file_inclusion_windows.txt -u http://mailing.htb/download.php?file=FUZZ

Content type header is need when fuzzing a POST

	ffuf -w usernames_to_delete.txt:USERNAME -X POST -d "username=USERNAME&password=admin2" -u http://report.solarlab.htb:6791/login -H "Content-Type: application/x-www-form-urlencoded"


## More Information

https://github.com/ffuf/ffuf/wiki
