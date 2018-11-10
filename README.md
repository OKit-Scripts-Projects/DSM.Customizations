# dsm-debian-chroot.spk
## Brief
I have fixed bugs for fitting dsm6.1~6.2,according to [this issue](https://github.com/SynoCommunity/spksrc/issues/1910)
Tested on my ds3615xs, dsm6.2.
And then I upload to my dropbox, 
you can download here, link below.
which include debian-chroot.spk and python.spk
## Instructions
The Web UI is not available.
SSH to your dsm, and input those commands below
Start Command:
`/var/packages/debian-chroot/scripts/start-stop-status start`
Chroot In Command:
`chroot /volume1/\@appstore/debian-chroot/var/chroottarget /bin/bash`
(`/volume1` should replced by your own application storage volume number)
Now, you are in debian-chroot.

## Download
[tenhow.debian-chroot.dsm6.[1/2].bromolow](https://www.dropbox.com/s/r4udr737knvv3jo/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.bromolow.zip?dl=0)

## P.S.
As I am using ds3615xs, I compiled this.
If you need other platforms, please make an issue, I would compile one for your platform later.
