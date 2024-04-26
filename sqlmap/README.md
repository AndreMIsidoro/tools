# sqlmap

## Overview

SQLMap is a free and open-source penetration testing tool written in Python that automates the process of detecting and exploiting SQL injection (SQLi) flaws. SQLMap has been continuously developed since 2006 and is still maintained today.

## Installation

	sudo apt install sqlmap
or
	git clone https://github.com/sqlmapproject/sqlmap.git


## Command Options

sqlmap

	-h, --help			Show basic help message and exit
	-hh			Show advanced help message and exit
	-u URL, --url=URL			Target URL
	--batch			Used for skipping any required user-input, by automatically choosing using the default option
	--dump			Dumps DBMS database table entries
	-p <injection_point>		Selects a specific injection point
	--os-shell		Try to get a remote shell on the server
	--is-dba		Check if we can get db admin priveledges
	-D <database_name>		Scans for a specific database
	-T <table_name>		Scans for a specific table


## Usage

sqlmap -u <address> --dump --batch
sqlmap -r <request_file_path> --dump --batch

if we dont find anything increase risk and level

sqlmap -r <request_file_path> --dump --batch --risk 3

sqlmap -r <request_file_path> --dump --batch --level 5

sqlmap -r <request_file_path> --dump --batch --level 5 --risk 3

Injection on a specific field

sqlmap -r <request_file_path> --batch -p <injection_field_name>