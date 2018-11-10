## fs.xfs
chroot in debian,then 
0. `apt install xfsprogs`
0. `fdisk /dev/sd* # create disk sd*1`
0. `mkfs.xfs -f /dev/sd*1`
then `exit` chroot,
0. `insmod xfs`
0. `mkdir /dataVol0`
0. `mount -t xfs /dev/sd*1 /dataVol0`
