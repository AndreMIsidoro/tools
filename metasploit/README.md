# Metasploit

## Overview

## Installation

	sudo apt update
	sudo apt install metasploit-framework


## Cookbook

Show post modules

	show post
	grep <pattern> show post

Run post module

	The exploit needs to be started in a session (use background in meterpreter or ctr+z in a normal shell)
	use <path_to_post>
	run session=<id_of_session_running_exploit>

Search exploits for specific version

	search <exploit> <version>
	example: search sudo 1.8.31

Open shell from meterpreter

	shell