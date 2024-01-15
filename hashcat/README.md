# hashcat

## usage

	hashcat -a <attack_mode> -m <hash_type> <wordlist_path>

	Use hashid <hash> -m to find the hash_type or https://hashcat.net/wiki/doku.php?id=example_hashes


## Examples

Using the rockyou.txt to break an hash

	hashcat -a 0 -m <hash_type> /usr/share/wordlist/rockyou.txt