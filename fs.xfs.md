# FileSystem.xfs
## Declares
0. My Main Storage Volume is `Volume2`
0. My Target Disk here is `/dev/sdc`

## Instructions
Chroot in debian, then 

0. `apt install xfsprogs`
0. `fdisk -l # Find your target disk` 
0. `fdisk /dev/sdc # create disk sdc1 # Here my target disk is sdc`
0. `n 1 w # Input the commands one by one`
0. `mkfs.xfs -f /dev/sdc1`

Then `exit` chroot,

0. `insmod xfs`
0. `mkdir /dataVol0`
0. `mount -t xfs /dev/sdc1 /dataVol0`

Then `mount -o bind` to System Folder

0. `mount -t xfs /dev/sdc1 /dataVol0`
0. Make a shared folder in DSM.WebUI.Shared_Folder module, called `data`
0. `mkdir -p /volume2/data/vol0`
0. `mount -o bind /dataVol0 /volume2/data/vol0`

### DS Audio
0. `mkdir -p /dataVol0/music`
0. Put some music in it above
0. Add `/volume*/homes/data/vol0/music` to your index on DSM.WebUI.Indexing_Service module
0. Click `Re-index Button` or `/usr/syno/bin/synoindex -R audio`


## Boot
0. In module WebUI.Task_Scheduler add boot-up script, input commands below
0. `insmod /xfs/xfs.ko`
0. `mount -t xfs /dev/sdc1 /dataVol0`
