# Department Folder Permissions Troubleshooting

## Problem

`employee01` could access the `General`, `IT`, and `HR` folders inside the `IT-Shared` network share.

The goal was to restrict employees so they could only access the department folder they belonged to.

## Investigation

I reviewed the NTFS permissions on the department folders and found that permissions from the `IT-Shared` parent folder were being inherited by the child folders.

This allowed `Domain Users` to retain access to the `IT` and `HR` folders even though `employee01` was only a member of `General-Employees`.

## Resolution

I disabled permission inheritance on the `IT` and `HR` folders and removed `Domain Users` from their NTFS permissions.

The department security groups were left with Modify permissions on their respective folders:

* `General-Employees` → General
* `IT-Department` → IT
* `HR-Department` → HR

## Verification

I logged into `WS-EMPLOYEE01` as `ITLAB\employee01` and verified the following:

* `General` → Accessible and writable
* `IT` → Access denied
* `HR` → Access denied

The department folders now restrict access based on the user's department security group.
