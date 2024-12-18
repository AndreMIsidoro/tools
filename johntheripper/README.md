# JohnTheRipper

## Overview

John the Ripper is a fast password cracker

## Command Options

	-w : Path to which wordlist to use

## Usage

First try to crack the file with the rockyou wordlist.

If it fails, append the --rules flag

	john <file_to_crack> --wordlist=/usr/share/rockyou.txt --rules

If this fails, try the default bruteforce, with no options and no wordlist:

	john <file_to_crack>


## Cookbook

Select wordlist and crack hash in file

	john -w=<path_to_word_list> <path_to_hash_file>

	Example: john -w=/usr/share/wordlists/rockyou.txt hash.txt

Crack zip password file

	zip2john <file>.zip > fileName.john
	john --show fileName.john

Crak id_rsa private keys

	ssh2john id_rsa > id_rsa.hash
	john id_rsa.hash --wordlist=/usr/share/wordlists/rockyou.txt

Crack .doc files

	office2john <filename>.doc > doc_file_hash

	john doc_file_hash --wordlist=/usr/share/wordlists/rockyou.txt