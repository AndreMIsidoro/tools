# THC Hydra



## Cookbook

How to run hydra to try passwords agains a service (like ssh):

	hydra -L usernames.txt -p 'password' {target_ip} service_name