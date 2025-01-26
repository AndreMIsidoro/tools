# THC Hydra



## Usage

How to run hydra to try passwords agains a service (like ssh):

	hydra -L usernames.txt -p 'password' {target_ip} service_name

Bruteforce web requests:

	hydra -l admin -P rockyou.txt -f 94.237.54.42 -s 54747 http-post-form "/:username=^USER^&password=^PASS^:F=Invalid credentials"