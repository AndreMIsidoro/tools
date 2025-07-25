# Impacket dpapi

## Overview

## Usage

To decrypt the dpapi credential we need two file: The master key located on C:\Users\<username>\AppData\Roaming\Microsoft\Protect\<SID>\
 and encrypted data that can be found in Vault files, rdp files, browser data, windows credential manager,etc.


First we decrypt the master key:

```shell
impacket-dpapi masterkey -file 08949382-134f-4c63-b93c-ce52efc0aa88 -sid S-1-5-21-3927696377-1337352550-2781715495-1110 -password NightT1meP1dg3on14
```

This will give us the decrypted master key, that we can now use on the credential file:

```shell
impacket-dpapi credential -file 772275FAD58525253490A9B0039791D3 -key 0xd2832547d1d5e0a01ef271ede2d299248d1cb0320061fd5355fea2907f9cf879d10c9f329c77c4fd0b9bf83a9e240ce2b8a9dfb92a0d15969ccae6f550650a83
```