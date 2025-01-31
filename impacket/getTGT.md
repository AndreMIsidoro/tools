# impacket-getTGT

The getTGT tool specifically is used to request a Ticket Granting Ticket (TGT) from a Kerberos Key Distribution Center (KDC) within a Windows domain.

## Usage

```
impacket-getTGT <domain>/<username>:<password>
```

Getting a ticket with NTLM hash:

```
impacket-getTGT  -hashes :<ntlm_hash> <domain>/'<username>'
impacket-getTGT  -hashes :aad3b435b51404eeaad3b435b51404ee vintage.htb/'GMSA01$'
```