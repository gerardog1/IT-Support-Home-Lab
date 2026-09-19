# IT-Support-Home-Lab

A hands-on IT support lab built with Microsoft Hyper-V and Windows Server to practice Windows administration, networking, Active Directory, DNS, DHCP, user and group management, file sharing, permissions, and troubleshooting.

## Lab Overview

This project simulates a small business Windows environment with an employee workstation and a Windows Server domain controller.

### Environment

* **Virtualization:** Microsoft Hyper-V
* **Workstation:** Windows 11 — `WS-EMPLOYEE01`
* **Server:** Windows Server 2022 — `DC01`
* **Domain:** `itlab.local`
* **Network:** Isolated Hyper-V internal network — `IT-LAB`

## Infrastructure

### Windows Server — DC01

Configured as the primary infrastructure server for the lab.

* Active Directory Domain Services (AD DS)
* DNS
* DHCP
* Domain: `itlab.local`
* Static IP: `192.168.10.10`
* DHCP scope: `192.168.10.100–192.168.10.200`

### Windows 11 — WS-EMPLOYEE01

Configured as a domain-joined employee workstation.

* Joined to `itlab.local`
* Receives network configuration through DHCP
* Uses DC01 for DNS
* Domain user: `ITLAB\employee01`

## Active Directory

Created and managed:

* Domain users
* Security groups
* Department-based groups
* Standard employee account

Groups created:

* `IT-Department`
* `HR-Department`
* `General-Employees`

`employee01` was assigned to the `General-Employees` group.

## File Sharing & Permissions

Created and configured the `IT-Shared` network share on DC01.

Practiced:

* SMB network shares
* NTFS permissions
* Share permissions
* Permission inheritance
* Security group-based access
* Department-specific folder access

Department folders:

* `General`
* `IT`
* `HR`

The final configuration restricts access based on department membership.

## Mapped Network Drive

Mapped the `IT-Shared` network share to:

```text
S:
```

Network path:

```text
\\DC01\IT-Shared
```

The drive is configured to reconnect automatically at sign-in.

## Troubleshooting Scenarios

### APIPA / DHCP Failure

The Windows workstation initially received a `169.254.x.x` APIPA address because no DHCP server was available.

Investigated the IP configuration and identified the lack of DHCP service on the isolated network.

[View Scenario](Troubleshooting-Scenarios/apipa-no-dhcp.md)

### Network Share Permissions

Investigated a situation where a domain user could access a network share but could not create files.

Separated the share-permission and NTFS-permission layers and corrected the configuration.

[View Scenario](Troubleshooting-Scenarios/network-share-permissions.md)

### Department Folder Permissions

Investigated why a user could access department folders they were not intended to access.

Identified inherited permissions from the parent share and configured department folders with appropriate security-group permissions.

[View Scenario](Troubleshooting-Scenarios/department-folder-permissions.md)

## Skills Practiced

* Windows 11 administration
* Windows Server administration
* Hyper-V
* Active Directory
* DNS
* DHCP
* TCP/IP troubleshooting
* Domain joining
* User and group management
* NTFS permissions
* SMB file sharing
* Permission inheritance
* Network drive mapping
* Command-line troubleshooting
* Event Viewer
* Device Manager
* Basic helpdesk troubleshooting

## Project Goal

The purpose of this lab is to build practical experience with common Windows IT support tasks in a controlled environment and document the troubleshooting process used to identify and resolve problems.
