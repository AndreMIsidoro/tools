# chisel

## Overview

	Chisel is a fast TCP/UDP tunnel, transported over HTTP, secured via SSH. Single executable including both client and server. Written in Go (golang). Chisel is mainly useful for passing through firewalls, though it can also be used to provide a secure endpoint into your network.

## Usage

Lets consider we want to reflect port 8000

	./chisel server -port 7777 --reverse 
	This will be the server that will listen for the reflection

	./chisel client <server_ip>:7777 R:8000:127.0.0.1:8000


## More Information

	https://github.com/jpillora/chisel
	https://book.hacktricks.xyz/generic-methodologies-and-resources/tunneling-and-port-forwarding#chisel