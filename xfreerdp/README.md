# xfreerdp

## Overview

xfreerdp is an X11 Remote Desktop Protocol (RDP) client which is part of the FreeRDP project. An RDP server is built-in to many editions of Windows. Alternative servers included xrdp and VRDP (VirtualBox).

## Installation

	sudo apt-get install freerdp3-x11

## Command Options

	/v:{target_IP} : Specifies the target IP of the host we would like to connect to.
	/cert:ignore : Specifies to the scrips that all security certificate usage should be ignored.
	/u:Administrator : Specifies the login username to be "Administrator".
	/p <password> : Specifies the password for the user


## Usage

Simple login

```shell
xfreerdp /v:<ip> /u:<username> /p:<password>
```

Login and setup a drive:

```shell
xfreerdp /v:<ip> /u:<username> /p:<password> /drive:<remote_path_to_drive>,"<local_path_to_be_staged"
#example
xfreerdp /v:127.0.0.1:13389 /u:hporter /p:Gr8hambino! /drive:home,"/home/tester/tools"
```


## Use xfreerdp inside docker container

First allow connections to X server:

```shell
xhost +local:docker
```

Run container:
```shell
docker run -it -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix ubuntu:22.04 /bin/bash
```
Then install xfreerdp2 (or 3):

```shell
apt update
apt install -y freerdp2-x11
```
Finally connect to server:

```shell
xfreerdp /v:10.129.234.51 /dynamic-resolution +clipboard -sec-nla
```
