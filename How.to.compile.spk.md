# How.to.compile.spk

## Brief
0. This is a step-by-step tutoril for compiling package, I use Debian-Chroot as an example. 
0. If you have other questions, pleae just make an issue at this repository.

## Prepares
0. Any OS which supported Docker (such as Debian, Windows, DSM6 with docker.)

## Declares
0. I use Debian 9 as host OS
0. With Docker CE installed
0. I use `~/compiles/spk` as the compile working directory
0. I called the docker container `spk`
0. I am compiling `syno-bromolow-6.1` which is for DS3615xs DSM6.1.

## Host Things
0. `docker pull synocommunity/spksrc`
0. `mkdir -p ~/compiles/spk # Use this Directory for store docker spk root`
0. Copy the whole code block below to terminal for start a container 'spk'
``` 
docker run -idt \
     --name spk \
     -v ~/compiles/spk:/spksrc \
     synocommunity/spksrc
```
3. `docker exec -ti spk /bin/bash # This command makes you can get in `spk` container at anytime`  

Now, we are in the Container 'spk'.

## Container 'spk' Things
Then do follow things in docker container 'spk'.

### Init (Spk Source and Toolchain)
0. `git clone https://github.com/SynoCommunity/spksrc.git /spksrc`
0. `cd /spksrc/kernel/syno-bromolow-6.1`
0. `make` # Then wait for a long time.

### Modify ToolChain Directory
0. `cd /spksrc/toolchains`
0. `rm syno-bromolow-`
0. `cp -rp syno-bromolow-6.1 syno-bromolow-`

Attention that `syno-bromolow-` is correct, do not add any other things

### Modify Debian-Chroot
0. `cd /spksrc/spk/debian-chroot/src/app`
0. `vim debian-chroot.js`
0. Copy `:0,$s/3rdparty\/debian-chroot/webman\/3rdparty\/debian-chroot/g` then just paste and enter, just one time.For mods. 
0. Copy `ZZ` then just paste, for closing the file and saving the mods.
0. Now, you have finished modify the Debian-Chroot for being compatible with DSM6.[1/2]. 

### Compile Debian-Chroot
0. `cd /spksrc/spk/debian-chroot`
0. `make ARCH="bromolow"`

#### Other Platforms
0. If you are other platforms, like apollolake, not supported by the official. You should modify Makefile.
0. We get info that apollolake is x64 arch.
0. `cd /spksrc/spk/debian-chroot`
0. `vim Makefile`
0. Find the line `DEBIAN_ARCH = amd64`, as apollolake is x64 arch. 
0. see the line over it : `ifeq ($(findstring $(ARCH),braswell bromolow cedarview x86 avoton x64),$(ARCH))`
0. Change the line above: `ifeq ($(findstring $(ARCH),braswell bromolow cedarview x86 avoton x64 apollolake),$(ARCH))`
0. Then save and `make ARCH="apollolake"`

### Find Packages Compiled
A long time later, the compile has been finished.

0. `cd /spksrc/packages`
0. `ls`
0. Then you will see the package you just compiled
0. Just like `debian-chroot_bromolow-_8.4-7.spk`

## Copy Packages To Host's Directory
For copy the package to your Home Directory or other places on your host OS, do the things below.

0. `exit` for exit from docker container 'spk'.
0. `docker container cp spk:/spksrc/packages/debian-chroot_bromolow-_8.4-7.spk ~/` 

## Copy Packages Out To Other Computers' Directory
Just use your way, many ways to copy it to your dest computers.

0. smb    
0. ftp
0. sftp
0. scp, sz
...

## References
### Docker Ref.
0. `docker ps`
0. `docker start spk`
0. `docker exec -ti spk /bin/bash`
0. `docker container cp spk:/spksrc/packages/debian-chroot_bromolow-_8.4-7.spk ~/`
0. `docker stop spk`

