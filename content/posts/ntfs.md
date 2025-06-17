+++
title = "NTFS File System"
date = "2025-04-02T10:36:37+02:00"
tags = ["Linux", "Windows", "Filesystem", "Errors Fixes", ]
draft = true
+++

NTFS, officially NT File System but commonly called New Technology File System,
is a Microsoft filesystem that has been the default on Windows since Windows NT 3.1.
Support for NTFS has been incorporated into the Linux kernel in version 5.15.0 that was released 31.10.2021.

<!--more-->

## Troubleshooting
### Error:
### mount: {mountpoint}/: fsconfig() failed: /dev/{device}: Can't lookup blockdev.
###        dmesg(1) may have more information after failed mount system call.
### Fix:

### Error:
### ntfs-3g-mount: failed to access mountpoint {/path/to/mountpoint}: Transport endpoint is not connected
### Fix:

### Error:
### bad superblock on device '/dev/{device}'
### mount: {mountpoint}: wrong fs type, bad option, bad superblock on /dev/{device}, missing codepage or helper program, or other error.
###        dmesg(1) may have more information after failed mount system call.
### Fix:

<!--end-->
