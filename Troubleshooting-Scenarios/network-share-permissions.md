# Network Share Permissions Troubleshooting

## Problem

`employee01` was able to open the `IT-Shared` network share but was unable to create a file inside it.

## Investigation

I verified that the `IT-Shared` folder was shared from `C:\IT-Shared` on the domain controller.

I checked the folder's NTFS permissions and found that `ITLAB\Users` had Read & Execute, List Folder Contents, and Read permissions.

I then added `Domain Users` with Modify permissions to allow domain users to create and modify files.

The issue persisted because the network share permissions were still configured as Read only for Everyone.

I changed the share permissions for Everyone to Full Control while using NTFS permissions to control the specific access level.

## Root Cause

The user was able to access the network share but could not create files because the share permissions were more restrictive than the NTFS permissions.

## Resolution

The share permissions were changed to allow Full Control for Everyone, while NTFS permissions for Domain Users were set to Modify.

After the changes, `employee01` was able to create and save a test file in the shared folder.

## Verification

A test file was successfully created from `WS-EMPLOYEE01` using the `ITLAB\employee01` account.
