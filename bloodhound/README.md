# bloodhound

## Overview

BloodHound uses graph theory to reveal the hidden and often unintended relationships within an Active Directory or Azure environment. Attackers can use BloodHound to easily identify highly complex attack paths that would otherwise be impossible to quickly identify. Defenders can use BloodHound to identify and eliminate those same attack paths. Both blue and red teams can use BloodHound to easily gain a deeper understanding of privilege relationships in an Active Directory or Azure environment.


## Installation

    pip install bloodhound


## Usage

    bloodhound-python -d <domain_name> -c all -u <username> -p <password> -ns <target_ip> --zip

# More Information

https://github.com/BloodHoundAD/BloodHound
https://github.com/dirkjanm/BloodHound.py