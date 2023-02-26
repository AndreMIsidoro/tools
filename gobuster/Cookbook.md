### User a worldlist to do a dir busting

	gobuster dir -w /usr/share/wordlists/dirb/common.txt -u <target_ip>

### Worldlist to bust dirs of a web server

	gobuster dir -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -u <target_ip>
