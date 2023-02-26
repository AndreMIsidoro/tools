# gobuster

## Overview

Gobuster is a tool used to brute-force:

	URIs (directories and files) in web sites.
	DNS subdomains (with wildcard support).
	Virtual Host names on target web servers.
	Open Amazon S3 buckets
	Open Google Cloud buckets
	TFTP servers


## Installation

First, you need to make sure you have Go installed on your Linux distribution, which is the programming
language used to write the gobuster tool.

	sudo apt install golang-go
	Add export PATH="$HOME/go/bin:$PATH" to ~/.bashrc

Then install gobuster

	go install github.com/OJ/gobuster/v3@latest

In case this fails, you can always compile the tool from its' source code by running the following commands:

	sudo git clone https://github.com/OJ/gobuster.git
	cd gobuster
	go get && go build
	go install

## Command Options

	dir : specify we are using the directory busting mode of the tool
		-w : specify a wordlist, a collection of common directory names that are typically used for sites
		-u : specify the target's IP address
		-x : File extensions to search for
		-o : specify output file (still prints to the stdoutput)
