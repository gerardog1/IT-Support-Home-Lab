# APIPA / DHCP Troubleshooting

## Problem

The Windows 11 workstation was unable to access the network after being connected to the `IT-LAB` virtual switch in Hyper-V.

Running `ipconfig` showed a `169.254.x.x` IPv4 address, with no default gateway or DNS servers listed.

This indicated that the workstation was not receiving a valid IP configuration from a DHCP server.

## Investigation

I checked the workstation's network configuration using `ipconfig`.

The workstation had:

* An IPv4 address in the `169.254.x.x` range
* No default gateway
* No DNS servers listed

A `169.254.x.x` address is an APIPA address, which Windows assigns to itself when it cannot obtain an IP address from a DHCP server.

The Hyper-V network adapter was connected to the `IT-LAB` internal virtual switch. The switch did not have a DHCP server providing IP addresses to the workstation.
