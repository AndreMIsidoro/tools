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
