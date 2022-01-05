# vmdk-mount

A shell script to mount partitions in .vmdk virtual disk.

## Prerequisite

Please make sure you had install "vmware" and `/usr/bin/vmware-mount` exists.



## Usage

## Test

There is a `vmdk_demo.vmdk` in `./demo`.

There are three partitions in `vmdk_demo.vmdk`:

* A `LUKS ext4 partition` which passphrase is `kaka2021#` starts at sector **2048** (2048*512 = 1048576) and sizes 100M.

* A `LUKS ext4 partition` which passphrase is `kaka2021#` start at sector **2048\*101 = 206848** (206848*512 = 105906176) and sizes 200M.

* A normal `btrfs partition` starts at **2048\*301 = 616448** (616448*512 = 315621376) sizes 63.71G

You may dump the partition info by `vmware-mount`

```
#vmware-mount vmdk-demo.vmdk
Nr      Start       Size Type Id Sytem
-- ---------- ---------- ---- -- ------------------------
 1       2048     204800  GPT EE Linux FS
 2     206848     204800  GPT EE Linux FS
 3     616448  133599232  GPT EE Linux FS
```


