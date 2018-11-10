# FileSystem.xfs
## Instructions
chroot in debian,then 

0. `apt install xfsprogs`
0. `fdisk /dev/sd* # create disk sd*1`
0. `mkfs.xfs -f /dev/sd*1`

then `exit` chroot,

0. `insmod xfs`
0. `mkdir /dataVol0`
0. `mount -t xfs /dev/sd*1 /dataVol0`

then `mount -o bind` to System Home Folder
0. `mount -t xfs /dev/sd*1 /dataVol0`
0. `mkdir -p /volume*/homes/data/vol0`
0. `mount -o bind /dataVol0 /volume*/homes/data/vol0`

## Example 
0. `mount -t xfs /dev/sdc1 /dataVol0`
0. `mkdir -p /volume2/homes/data/vol0`
0. `mount -o bind /dataVol0 /volume2/homes/data/vol0`
