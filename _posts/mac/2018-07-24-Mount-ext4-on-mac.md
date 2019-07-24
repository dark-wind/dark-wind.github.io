---
title: 'Mount ext4 filesystem on macOS'
categories: mac
tags: ext4 mac fuse
---

1) Install ext4fuse.

```
brew cask install osxfuse
brew install ext4fuse
```

2) Select partition.

```
diskutil list

/dev/disk3 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *3.0 TB     disk3
   1:       Microsoft Basic Data                         3.0 TB     disk3s1
```

3) Mount.

```
sudo ext4fuse /dev/disk3s1 ~/Disk -o allow_other
```


