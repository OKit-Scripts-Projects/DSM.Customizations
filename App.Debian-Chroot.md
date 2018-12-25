# DSM.debian-chroot.spk
## Brief
I have fixed bugs for fitting dsm6.1~6.2,according to [this issue](https://github.com/SynoCommunity/spksrc/issues/1910)
Tested on my ds3615xs, dsm6.2.

And then I upload to my dropbox, you can download here, link below.

which include debian-chroot.spk and python.spk

## Declares
0. I use volume2 as my application storage volume, many are volume1. so you should change it by yourself.

## Instructions
***The Web UI Status Tab is not available.But the service tab seems available***

***Try to use shell totally***

SSH to your DSM6.x, and input those commands below

0. `/var/packages/debian-chroot/scripts/start-stop-status start # Start Command`
1. `chroot /volume2/\@appstore/debian-chroot/var/chroottarget /bin/bash # Chroot In Command, change volume2 to your exact volume`

(`/volume2` should replaced by your own application storage volume number)

Now, you are in debian-chroot.

## Attention
0. Somebody meet some problem after installing this package, sometimes a Reboot is needed.

## Downloads
0. [Tenhow.debian-chroot.dsm6.[1/2].bromolow](https://www.dropbox.com/s/r4udr737knvv3jo/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.bromolow.zip?dl=0) [as DS3615xs] [Required by myself] √
0. [Tenhow.debian-chroot.dsm6.[1/2].apollolake](https://www.dropbox.com/s/aef5a6a70tparbc/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.apollolake.zip?dl=0) [as DS918+] [Required by lordvalium] √
0. [Tenhow.debian-chroot.dsm6.[1/2].cedarview](https://www.dropbox.com/s/85kzm6pgm90imnr/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.cedarview.zip?dl=0) [as DS1213+] [Required by Tao87-04] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armadaxp](https://www.dropbox.com/s/04ivz8nfztg2fe9/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.armadaxp.zip?dl=0) [as RS815] [Required by DzikNsk] [No Feedback Yet]
0. [Tenhow.debian-chroot.dsm6.[1/2].88f628x](https://www.dropbox.com/s/w4psq4m4dgpdy4m/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.88f628x.zip?dl=0) [as DS212] [Required by balabalaman] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armada375](https://www.dropbox.com/s/6oc6ioc2c7abqti/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.rtd1296.zip?dl=0) [as DS215j] [Required by paul-xor] √
0. [Tenhow.debian-chroot.dsm6.[1/2].monaco](https://www.dropbox.com/s/3a6ocgfvdshzixr/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.monaco.zip?dl=0) [as DS216play] [Required by d4n1elchen] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armada38x](https://www.dropbox.com/s/71p8e49dwbuv3zu/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.armada38x.zip?dl=0) [as DS216j] [Required by d4n1elchen] √
0. [Tenhow.debian-chroot.dsm6.[1/2].rtd1296](https://www.dropbox.com/s/6oc6ioc2c7abqti/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.rtd1296.zip?dl=0) [as DS418] [Required by gypittmann] [!Not Tested Yet!] 
0. [Tenhow.debian-chroot.dsm6.[1/2].avaton](https://www.dropbox.com/s/qroxml7bi7xy2oq/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.avoton.zip?dl=0) [as DS1817+] [Required by droidboxma] √




## Platform
As I am using ds3615xs, I compiled this.

If you need other platforms, just make an new issue, I would compile one for your platform later in my free time.

## Optimize
0. `apt update`
0. `apt upgrade`
0. `dpkg-reconfigure tzdata`
0. `apt install locales`
0. `dpkg-reconfigure locales`

## Request
If this repository helped, please give it a star, indicating this repository is helpfull.

Happy hacking! 

## References
0. [What_kind_of_CPU_does_my_NAS_have](https://www.synology.com/zh-tw/knowledgebase/DSM/tutorial/General/What_kind_of_CPU_does_my_NAS_have)

