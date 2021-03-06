# bdsync #

## NAME ##

bdsync - a fast block device synchronizing tool

## SYNOPSIS ##

    Client: bdsync [--verbose] REMSHCMD LOCDEV REMDEV
    Server: bdsync --server [--verbose]
    Patch:  bdsync --patch [--verbose] [DSTDEV]

## DESCRIPTION ##

Bdsync can be used to synchronize block devices over a network. It generates
a "binary diff" in an efficient way by comparing MD5 checksums of 32k blocks
of the local block device LOCDEV and the remote block device REMDEV.  

This binary diff can be sent to the remote machine and applied to its block
device DSTDEV, after which the local blockdev LOCDEV and the remote block 
device REMDEV are synchronized.  

bdsync was built to do the only thing rsync isn't able to do: synchronize block
devices.
