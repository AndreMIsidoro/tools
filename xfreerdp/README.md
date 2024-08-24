# xfreeredp

## Overview

xfreerdp is an X11 Remote Desktop Protocol (RDP) client which is part of the FreeRDP project. An RDP server is built-in to many editions of Windows. Alternative servers included xrdp and VRDP (VirtualBox).

## Installation

	sudo apt-get install freerdp2-x11

## Command Options

	/v:{target_IP} : Specifies the target IP of the host we would like to connect to.
	/cert:ignore : Specifies to the scrips that all security certificate usage should be ignored.
	/u:Administrator : Specifies the login username to be "Administrator".
	/p <password> : Specifies the password for the user


## Usage

Simple login

	xfreerdp /v:<ip> /u:<username> /p:<password>
