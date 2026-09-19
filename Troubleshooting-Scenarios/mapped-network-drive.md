# Mapped Network Drive

## Overview

I mapped the `IT-Shared` network share to the `S:` drive on `WS-EMPLOYEE01` for the `employee01` domain account.

## Configuration

* **Drive:** `S:`
* **Network path:** `\\DC01\IT-Shared`
* **User:** `ITLAB\employee01`
* **Reconnect at sign-in:** Enabled

## Verification

After signing in as `ITLAB\employee01`, the `S:` drive was available in File Explorer and provided access to the `IT-Shared` network share.

The mapped drive provides the employee with a convenient way to access the shared network resources without manually entering the UNC path.
