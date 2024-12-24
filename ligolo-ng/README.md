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

    ./proxy -selfcert

Then on the machine MS01, start the agent:

    agent.exe --connect <ip_of _the_proxy>:<port_of_the_proxy> -retry -ignore-cert

Back on the proxy, after the agent has joined:

    session
    <choose the session for the agent that just connected>
    start

Then add the route to DC01 to the interface:

    sudo ip route add <subnet_mask_dc01> dev ligolo
    sudo ip route add 10.10.1.0/24 dev ligolo

Finally you should be able now to simple do:

    ping DC01

And the icmp packets will be route through MS01 to DC01


## More Information

https://github.com/nicocha30/ligolo-ng