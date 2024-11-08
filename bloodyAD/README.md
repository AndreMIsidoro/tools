# bloodyAD

## Overview

This tool can perform specific LDAP calls to a domain controller in order to perform AD privesc.

bloodyAD supports authentication using cleartext passwords, pass-the-hash, pass-the-ticket or certificates and binds to LDAP services of a domain controller to perform AD privesc.

## Installation

pip install bloodyAD

## Usage

Set owener of group

    bloodyAD --host <host_ip> -d '<domain_name>' -u '<username>' -p '<password>' set owner <group_name> <name_of_new_owner>