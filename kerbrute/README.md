# kerbrute

## Overview

A tool to quickly bruteforce and enumerate valid Active Directory accounts through Kerberos Pre-Authentication

## Installation

Download the latest version of Go from the official website: https://golang.org/dl/

Use the wget Command to download the package, extrackt and set up path:

    wget https://dl.google.com/go/go1.x.linux-amd64.tar.gz

    tar -xvf go1.x.linux-amd64.tar.gz

    sudo mv go /usr/local

    export PATH=$PATH:/usr/local/go/bin

    source ~/.zshrc
    go version


## Usage

    kerbrute userenum --dc <ip_to_domain_controller> -d <full_domain_name> <path_to_file_with_usernames>
        kerbrute username --dc 10.10.10.10 -d jab.htb usernames.txt



## More Information


https://github.com/ropnop/kerbrute