# JohnTheRipper Cookbook

### Select wordlist and crack hash in file

	john -w=<path_to_word_list> <path_to_hash_file>

	Example: john -w=/usr/share/wordlists/rockyou.txt hash.txt
