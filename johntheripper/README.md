# JohnTheRipper

## Overview

John the Ripper is a fast password cracker

## Command Options

	-w : Path to which wordlist to use

## Word Lists

Rock You

	Comes pre installed in Kali in /usr/share/wordlists/rockyou.txt
	https://github.com/josuamarcelc/common-password-list

## Cookbook

Select wordlist and crack hash in file

	john -w=<path_to_word_list> <path_to_hash_file>

	Example: john -w=/usr/share/wordlists/rockyou.txt hash.txt

Crack zip password file

	zip2john <file>.zip > fileName.john
	john --show fileName.john