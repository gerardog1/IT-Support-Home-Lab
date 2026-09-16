# Windows 11 Workstation

## Overview

This virtual machine serves as the primary employee workstation in my IT Support Home Lab.

The lab is designed to provide hands-on practice with Windows administration, troubleshooting, networking, and simulated end-user support scenarios.

## Environment

* **Operating System:** Windows 11
* **Virtualization Platform:** Microsoft Hyper-V
* **Network:** Hyper-V virtual network
* **Purpose:** Simulated employee workstation for IT support troubleshooting

## Baseline Verification

Before beginning troubleshooting scenarios, I verified that the workstation was functioning normally.

* Confirmed internet connectivity
* Checked IP configuration using `ipconfig`
* Tested network connectivity using `ping`
* Tested DNS resolution using `nslookup`
* Reviewed Task Manager
* Reviewed Device Manager
* Reviewed Event Viewer

A Hyper-V checkpoint was created to preserve the clean baseline state.

## Planned Use

This workstation will be used to simulate common helpdesk incidents involving:

* Network connectivity
* Windows configuration
* Applications
* User accounts and permissions
* Services
* System performance
* Troubleshooting and diagnostic tools

