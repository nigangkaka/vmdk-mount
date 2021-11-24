# vmdk-mount

A shell script to mount partitions in .vmdk virtual disk.

## Usage

## Test

There is a `vmdk_demo.vmdk` in `./demo`.

There are three partitions in `vmdk_demo.vmdk`:

* A `LUKS ext4 partition` which password is `kaka2021#` starts at sector **2048** (2048*512 = 1048576) and sizes 100M.

* A `LUKS ext4 partition` which password is `kaka2021#` start at sector **2048\*101 = 206848** (206848*512 = 105906176) and sizes 100M.

* A normal `btrfs partition` starts at **2048\*201 = 411648** (411648*512 = 210763776) sizes 63.80G

You may dump the partition info by `vmware-mount`

```
#vmware-mount vmdk-demo.vmdk
Nr      Start       Size Type Id Sytem
-- ---------- ---------- ---- -- ------------------------
 1       2048     204800  GPT EE Linux FS
 2     206848     204800  GPT EE Linux FS
 3     411648  133804032  GPT EE Linux FS
```


