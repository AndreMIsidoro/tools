# Impacket smb client

## Overview

## Usage

Show shares:

```shell
shares
```

Connect to smb using a TGT:

```shell
export KRB5CCNAME=~/workspace/tmp/voleur/todd.wolfe.ccache 
faketime "$(ntpdate -q voleur.htb | awk '{print $1" "$2}')" impacket-smbclient -k dc.voleur.htb
```