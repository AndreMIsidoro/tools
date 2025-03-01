# ligolo-ng

## Overview

Ligolo-ng is a simple, lightweight and fast tool that allows pentesters to establish tunnels from a reverse TCP/TLS connection using a tun interface (without the need of SOCKS).


## Usage

Example Scenario:

Lets say that we are connected to a vpn and we can talk with a machine called MS01. Then in this machine we can talk to a DC01. Ligolo can help us tunnel through MS01 directly to DC01, so that we can do from our local machine this:

    ping DC01

First download the ligolo agent to the MS01 machine and the ligolo proxy to run it in our local machine

Then in the localhost create the ligolo interface:

    sudo ip tuntap add user kali mode tun ligolo

Then start the interface:

    sudo ip link set ligolo up

Then start the proxy in the localhost:

    ./proxy -selfcert -laddr 0.0.0.0:<desired_proxy_port>

Then on the machine MS01, start the agent:

    agent.exe --connect <ip_of _the_proxy>:<port_of_the_proxy> -retry -ignore-cert

Back on the proxy, after the agent has joined:

    session
    <choose the session for the agent that just connected>
    start

Then add the route to DC01 to the interface:

    sudo ip route add <subnet_mask_dc01> dev ligolo

For example

    sudo ip route add 10.10.1.0/24 dev ligolo

Finally you should be able now to simple do:

    ping DC01

And the icmp packets will be route through MS01 to DC01

## Reverse Port Forward throgh agent to proxy

When the proxy is running in localhost. In a ligolo session, use the listener_add to start a reverse port forward through the agent to the proxy:

    listener_add --addr 0.0.0.0:1234 --to 127.0.0.1:4321 --tcp

This will create a TCP listening socket on the agent (0.0.0.0:1234) and redirect connections to the 4321 port of the proxy server.

## Cleaning up

After using ligolo, you can delete the created interface with:

```shell
sudo ip link delete ligolo
```

This will also delete the routes created.

## Tips

When using nmap, you should use --unprivileged or -PE to avoid false positives.

    nmap -Pn -oN dc01_nmap.out --unprivileged DC01.INLANEFREIGHT.LOCAL


## More Information

https://github.com/nicocha30/ligolo-ng