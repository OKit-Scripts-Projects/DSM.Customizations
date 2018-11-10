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
0. make a shared folder in DSM.WebUI.Shared_Folder module, called `data`
0. `mkdir -p /volume2/data/vol0`
0. `mount -o bind /dataVol0 /volume2/data/vol0`

### DS Audio
0. `mkdir -p /dataVol0/music`
0. Put some music in it above
0. Add `/volume*/homes/data/vol0/music` to your index on DSM.WebUI.Indexing_Service module
0. Click `Re-index Button` or `/usr/syno/bin/synoindex -R audio`
