# FileSystem.xfs
## Brief
I prefer `xfs` rather than `ext4` or `btrfs` for my disks, so I compiled a kernel module for xfs.

And here, I would make a tutoril for use `xfs` in DSM6.x

It's an advanced usage, if you like to use `xfs`, please make an issue at this repository for a `xfs.ko` or you can also compile by yourself. 

## Declares
0. My Main Storage Volume is `/volume2`
0. My Target Disk here is `/dev/sdc`

## Prepare
0. download or compile the xfs modules
0. transmit to your DSM
0. put xfs modules in `/xfs/xfs.ko`
0. install debian-chroot

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

## Boot
0. In module WebUI.Task_Scheduler add boot-up script, input commands below
0. `insmod /xfs/xfs.ko`
0. `mount -t xfs /dev/sdc1 /dataVol0`
0. `mount -o bind /dataVol0 /volume2/data/vol0`

## Check
Now check your setting, then reboot for checking again.
