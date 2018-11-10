# DSM.debian-chroot.spk
## Brief
I have fixed bugs for fitting dsm6.1~6.2,according to [this issue](https://github.com/SynoCommunity/spksrc/issues/1910)
Tested on my ds3615xs, dsm6.2.

And then I upload to my dropbox, you can download here, link below.

which include debian-chroot.spk and python.spk

## Declares
0. I use volume2 as my application storage volume, many are volume1. so you should change it by yourself.

## Instructions
***The Web UI Status Tab is not available.***

***Just use shell***

SSH to your dsm, and input those commands below

0. `/var/packages/debian-chroot/scripts/start-stop-status start # Start Command`
1. `chroot /volume2/\@appstore/debian-chroot/var/chroottarget /bin/bash # Chroot In Command, change volume2 to yours exact volume

(`/volume2` should replced by your own application storage volume number)

Now, you are in debian-chroot.

## Downloads
[Tenhow.debian-chroot.dsm6.[1/2].bromolow](https://www.dropbox.com/s/r4udr737knvv3jo/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.bromolow.zip?dl=0)

## Helps
As I am using ds3615xs, I compiled this.

If you need other platforms, please make an issue, I would compile one for your platform later.

## Optimize
0. `apt update`
0. `apt upgrade`
0. `dpkg-reconfigure tzdata`
0. `apt install locales`
0. `dpkg-reconfigure locales`

## For Chinese
If you are Chinese, you may would like to change your apt source to 163's
tzdata choose [asia/shanghai]

