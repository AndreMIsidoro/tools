### User a worldlist to do a dir busting

	gobuster dir -w /usr/share/wordlists/dirb/common.txt -u <target_ip>

### Worldlist to bust dirs of a web server

	gobuster dir -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -u <target_ip>

### Brute force virtual host domains

	gobuster vhost -w <wordlistpath> -u <target_ip> --append-domain <domain>
	
	Ex : gobuster vhost -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt -u <target_ip> --append-domain thtoppers.htb
