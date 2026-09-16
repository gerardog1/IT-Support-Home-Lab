# APIPA / DHCP Troubleshooting

## Problem

The Windows 11 workstation was unable to access the network after being connected to the `IT-LAB` virtual switch in Hyper-V.

Running `ipconfig` showed a `169.254.x.x` IPv4 address, with no default gateway or DNS servers listed.

This indicated that the workstation was not receiving a valid IP configuration from a DHCP server.

